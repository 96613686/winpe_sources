# GetShortcutTarget(ushort const *,ushort *,ushort *,ushort *)

- ea: `0x1800814d0`
- end: `0x180081a55`
- name: `?GetShortcutTarget@@YA?AW4Bool@@PEBGPEAG11@Z`
- size: `1413`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180081170`
- `0x1800e519c`
- `0x180197ef0`

## callees

- `0x180025a18`
- `0x180026ffc`
- `0x18004cf08`
- `0x180066074`
- `0x1800814d0`
- `0x180081a5c`
- `0x180081ae0`
- `0x180083178`
- `0x1800833ec`
- `0x1801382a0`
- `0x180146548`
- `0x18025ab2a`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180081a08`
- `KERNEL32!CloseHandle` at `0x180081a08`
- `KERNEL32!GetLastError` at `0x18008178d`
- `KERNEL32!GetLastError` at `0x18008178d`
- `KERNEL32!SetLastError` at `0x180081783`
- `KERNEL32!SetLastError` at `0x180081783`
- `KERNEL32!CreateFileW` at `0x180081701`
- `KERNEL32!CreateFileW` at `0x180081701`
- `KERNEL32!LocalFree` at `0x18008168c`
- `KERNEL32!LocalFree` at `0x18008168c`
- `KERNEL32!GetFileType` at `0x180081717`
- `KERNEL32!GetFileType` at `0x180081717`
- `KERNEL32!ReadFile` at `0x1800817d7`
- `KERNEL32!ReadFile` at `0x180081816`
- `KERNEL32!ReadFile` at `0x180081861`
- `KERNEL32!ReadFile` at `0x1800818d9`
- `KERNEL32!ReadFile` at `0x180081946`
- `KERNEL32!ReadFile` at `0x1800819c3`
- `KERNEL32!ReadFile` at `0x1800817d7`
- `KERNEL32!ReadFile` at `0x180081816`
- `KERNEL32!ReadFile` at `0x180081861`
- `KERNEL32!ReadFile` at `0x1800818d9`
- `KERNEL32!ReadFile` at `0x180081946`
- `KERNEL32!ReadFile` at `0x1800819c3`
- `KERNEL32!SetFilePointer` at `0x18008183d`
- `KERNEL32!SetFilePointer` at `0x180081893`
- `KERNEL32!SetFilePointer` at `0x180081910`
- `KERNEL32!SetFilePointer` at `0x180081978`
- `KERNEL32!SetFilePointer` at `0x18008183d`
- `KERNEL32!SetFilePointer` at `0x180081893`
- `KERNEL32!SetFilePointer` at `0x180081910`
- `KERNEL32!SetFilePointer` at `0x180081978`

## string_xrefs

- `0x18008173f`: `Error: This is not a valid file, hence failing to create: %s`

## pseudocode

```c
_BOOL8 __fastcall GetShortcutTarget(const WCHAR *a1, unsigned __int16 *a2, unsigned __int16 *a3, unsigned __int16 *a4)
{
  BOOL v8; // edi
  struct IUnknown *COMInterface; // rax
  struct IUnknown *v10; // r14
  int v11; // ebx
  int (__fastcall *v12)(_QWORD, GUID *, __int64 *); // r14
  bool v13; // bl
  bool v14; // cl
  int v15; // esi
  BOOL v16; // ebx
  HANDLE FileW; // rax
  void *v18; // rbx
  bool v19; // cl
  unsigned int v20; // edx
  int v21; // edi
  int v22; // esi
  int v23; // ecx
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v26[2]; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  int (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-90h] BYREF
  unsigned int v29; // [rsp+78h] [rbp-88h] BYREF
  HANDLE v30; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  __int64 v32; // [rsp+90h] [rbp-70h] BYREF
  _BYTE Buffer[20]; // [rsp+A0h] [rbp-60h] BYREF
  int v34; // [rsp+B4h] [rbp-4Ch]
  _BYTE v35[8]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v36[260]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 v37[266]; // [rsp+1FCh] [rbp+FCh] BYREF

  if ( !a1 )
    return 0;
  v8 = g_scServerContext == 2 && GetImpersonationFromPath(a1);
  COMInterface = CreateCOMInterface((const struct _GUID *)a1);
  v10 = COMInterface;
  if ( !COMInterface )
    return 0;
  v28 = 0;
  v27 = 0;
  v11 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD))COMInterface->lpVtbl->QueryInterface)(
          COMInterface,
          &IID_IShellLinkDataList,
          &v28);
  ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->Release)(v10);
  if ( v11 >= 0 && v28 )
  {
    v12 = **v28;
    v27 = 0;
    if ( v12(v28, &IID_IPersistFile, &v27) < 0 || !v27 )
    {
      v16 = 0;
      goto LABEL_62;
    }
    v13 = g_bHKCUIsSystem;
    if ( v8 )
      StartImpersonating();
    else
      LoadCurrentUserKey(1);
    v15 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, _QWORD))(*(_QWORD *)v27 + 40LL))(v27, a1, 0);
    if ( v8 )
      StopImpersonating(v14);
    else
      LoadCurrentUserKey(v13);
    if ( v15 >= 0 )
    {
      hMem = 0;
      if ( (*v28)[4](v28, (GUID *)2684354566LL, (__int64 *)&hMem) >= 0 )
      {
        if ( hMem )
        {
          v16 = DecomposeDescriptor((const unsigned __int16 *)hMem + 134, 1, a2, a3, a4, 0, 0, 0) != 0;
          LocalFree(hMem);
LABEL_62:
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v27);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v28);
          return v16;
        }
      }
    }
    goto LABEL_21;
  }
  if ( v8 )
    StartImpersonating();
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
  v30 = FileW;
  v18 = FileW;
  if ( FileW != (HANDLE)-1LL && GetFileType(FileW) - 2 <= 1 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"Error: This is not a valid file, hence failing to create: %s",
        a1,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    CHandle::operator=(&v30, -1);
    SetLastError(0x6Eu);
    v18 = v30;
  }
  GetLastError();
  if ( v8 )
    StopImpersonating(v19);
  if ( v18 != (void *)-1LL )
  {
    memset_0(Buffer, 0, 0x4Cu);
    v29 = 0;
    NumberOfBytesRead = 0;
    if ( !ReadFile(v18, Buffer, 0x4Cu, &NumberOfBytesRead, 0) || NumberOfBytesRead != 76 )
    {
      CloseHandle(v18);
LABEL_21:
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      if ( v28 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v28)[2])(v28);
      return 0;
    }
    if ( (v34 & 1) != 0 )
    {
      v26[0] = 0;
      if ( !ReadFile(v18, v26, 2u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 2 )
        goto LABEL_67;
      SetFilePointer(v18, v26[0], 0, 1u);
    }
    if ( (v34 & 2) == 0 )
      goto LABEL_47;
    if ( ReadFile(v18, &v29, 4u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 4 )
    {
      v20 = v29;
      if ( v29 >= 4 )
      {
        v29 -= 4;
        SetFilePointer(v18, v20 - 4, 0, 1u);
      }
LABEL_47:
      v21 = 0;
      v22 = v34 & 0x80;
      while ( 1 )
      {
        v23 = *((_DWORD *)qword_1802A7800 + v21);
        if ( !v23 )
          break;
        if ( (v23 & v34) != 0 )
        {
          v26[0] = 0;
          if ( !ReadFile(v18, v26, 2u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 2 )
            goto LABEL_67;
          SetFilePointer(v18, v26[0] * ((v22 != 0) + 1), 0, 1u);
        }
        ++v21;
      }
      memset_0(v35, 0, 0x314u);
      while ( 1 )
      {
        v32 = 0;
        if ( !ReadFile(v18, &v32, 8u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 8 )
          goto LABEL_60;
        if ( HIDWORD(v32) == -1610612730 )
          break;
        if ( (unsigned int)v32 <= 8 || SetFilePointer(v18, v32 - 8, 0, 1u) == -1 )
          goto LABEL_60;
      }
      if ( !ReadFile(v18, v36, 0x30Cu, &NumberOfBytesRead, 0) || NumberOfBytesRead != 780 )
      {
LABEL_60:
        v16 = 0;
        goto LABEL_61;
      }
      v16 = DecomposeDescriptor(v37, 1, a2, a3, a4, 0, 0, 0) != 0;
LABEL_61:
      CHandle::~CHandle((CHandle *)&v30);
      goto LABEL_62;
    }
  }
LABEL_67:
  CHandle::~CHandle((CHandle *)&v30);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v27);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v28);
  return 0;
}

```

## disassembly

```asm
0x1800814d0  push    rbp
0x1800814d2  push    rbx
0x1800814d3  push    rsi
0x1800814d4  push    rdi
0x1800814d5  push    r12
0x1800814d7  push    r13
0x1800814d9  push    r14
0x1800814db  push    r15
0x1800814dd  lea     rbp, [rsp-328h]
0x1800814e5  sub     rsp, 428h
0x1800814ec  mov     rax, cs:__security_cookie
0x1800814f3  xor     rax, rsp
0x1800814f6  mov     [rbp+360h+var_50], rax
0x1800814fd  mov     r13, r9
0x180081500  mov     r12, r8
0x180081503  mov     r15, rdx
0x180081506  mov     rsi, rcx
0x180081509  test    rcx, rcx
0x18008150c  jz      loc_180081A30
0x180081512  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x180081519  jnz     short loc_18008152B
0x18008151b  call    ?GetImpersonationFromPath@@YA_NPEBG@Z; GetImpersonationFromPath(ushort const *)
0x180081520  cmp     al, 1
0x180081522  jnz     short loc_18008152B
0x180081524  mov     edi, 1
0x180081529  jmp     short loc_18008152D
0x18008152b  xor     edi, edi
0x18008152d  call    ?CreateCOMInterface@@YAPEAUIUnknown@@AEBU_GUID@@@Z; CreateCOMInterface(_GUID const &)
0x180081532  mov     r14, rax
0x180081535  test    rax, rax
0x180081538  jz      loc_180081A30
0x18008153e  mov     [rsp+460h+var_3F0], 0
0x180081547  lea     r8, [rsp+460h+var_3F0]
0x18008154c  mov     [rsp+460h+var_3F8], 0
0x180081555  lea     rdx, IID_IShellLinkDataList
0x18008155c  mov     rcx, [rax]
0x18008155f  mov     rax, [rcx]
0x180081562  mov     rcx, r14
0x180081565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008156a  mov     rcx, [r14]
0x18008156d  mov     ebx, eax
0x18008156f  mov     rax, [rcx+10h]
0x180081573  mov     rcx, r14
0x180081576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008157b  xor     r14d, r14d
0x18008157e  test    ebx, ebx
0x180081580  js      loc_1800816D4
0x180081586  mov     rbx, [rsp+460h+var_3F0]
0x18008158b  test    rbx, rbx
0x18008158e  jz      loc_1800816D4
0x180081594  mov     rax, [rbx]
0x180081597  mov     rcx, [rsp+460h+var_3F8]
0x18008159c  mov     r14, [rax]
0x18008159f  test    rcx, rcx
0x1800815a2  jz      short loc_1800815B0
0x1800815a4  mov     rdx, [rcx]
0x1800815a7  mov     rax, [rdx+10h]
0x1800815ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800815b0  lea     r8, [rsp+460h+var_3F8]
0x1800815b5  mov     [rsp+460h+var_3F8], 0
0x1800815be  lea     rdx, IID_IPersistFile
0x1800815c5  mov     rcx, rbx
0x1800815c8  mov     rax, r14
0x1800815cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800815d0  xor     r14d, r14d
0x1800815d3  test    eax, eax
0x1800815d5  js      loc_1800816CC
0x1800815db  cmp     [rsp+460h+var_3F8], r14
0x1800815e0  jz      loc_1800816CC
0x1800815e6  mov     bl, cs:?g_bHKCUIsSystem@@3_NA; bool g_bHKCUIsSystem
0x1800815ec  test    edi, edi
0x1800815ee  jz      short loc_1800815F7
0x1800815f0  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x1800815f5  jmp     short loc_1800815FE
0x1800815f7  mov     cl, 1; bool
0x1800815f9  call    ?LoadCurrentUserKey@@YA_N_N@Z; LoadCurrentUserKey(bool)
0x1800815fe  mov     rcx, [rsp+460h+var_3F8]
0x180081603  xor     r8d, r8d
0x180081606  mov     rdx, rsi
0x180081609  mov     rax, [rcx]
0x18008160c  mov     rax, [rax+28h]
0x180081610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081615  mov     esi, eax
0x180081617  test    edi, edi
0x180081619  jz      short loc_180081622
0x18008161b  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x180081620  jmp     short loc_180081629
0x180081622  mov     cl, bl; bool
0x180081624  call    ?LoadCurrentUserKey@@YA_N_N@Z; LoadCurrentUserKey(bool)
0x180081629  test    esi, esi
0x18008162b  js      short loc_180081697
0x18008162d  mov     rcx, [rsp+460h+var_3F0]
0x180081632  lea     r8, [rbp+360h+hMem]
0x180081636  mov     [rbp+360h+hMem], r14
0x18008163a  mov     edx, 0A0000006h
0x18008163f  mov     rax, [rcx]
0x180081642  mov     rax, [rax+20h]
0x180081646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008164b  test    eax, eax
0x18008164d  js      short loc_180081697
0x18008164f  mov     rcx, [rbp+360h+hMem]
0x180081653  test    rcx, rcx
0x180081656  jz      short loc_180081697
0x180081658  mov     [rsp+460h+var_428], r14; bool *
0x18008165d  add     rcx, 10Ch; unsigned __int16 *
0x180081664  mov     [rsp+460h+hTemplateFile], r14; unsigned int *
0x180081669  mov     r9, r12; unsigned __int16 *
0x18008166c  mov     qword ptr [rsp+460h+dwFlagsAndAttributes], r14; unsigned int *
0x180081671  mov     r8, r15; unsigned __int16 *
0x180081674  mov     dl, 1; bool
0x180081676  mov     qword ptr [rsp+460h+dwCreationDisposition], r13; unsigned __int16 *
0x18008167b  call    ?DecomposeDescriptor@@YAHPEBG_NPEAG22PEAK3PEA_N@Z; DecomposeDescriptor(ushort const *,bool,ushort *,ushort *,ushort *,ulong *,ulong *,bool *)
0x180081680  mov     rcx, [rbp+360h+hMem]; hMem
0x180081684  test    eax, eax
0x180081686  mov     ebx, r14d
0x180081689  setnz   bl
0x18008168c  call    cs:__imp_LocalFree
0x180081692  jmp     loc_18008198F
0x180081697  mov     rcx, [rsp+460h+var_3F8]
0x18008169c  test    rcx, rcx
0x18008169f  jz      short loc_1800816AD
0x1800816a1  mov     rax, [rcx]
0x1800816a4  mov     rax, [rax+10h]
0x1800816a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800816ad  mov     rcx, [rsp+460h+var_3F0]
0x1800816b2  test    rcx, rcx
0x1800816b5  jz      loc_180081A30
0x1800816bb  mov     rax, [rcx]
0x1800816be  mov     rax, [rax+10h]
0x1800816c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800816c7  jmp     loc_180081A30
0x1800816cc  mov     ebx, r14d
0x1800816cf  jmp     loc_18008198F
0x1800816d4  test    edi, edi
0x1800816d6  jz      short loc_1800816DD
0x1800816d8  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x1800816dd  xor     r9d, r9d; lpSecurityAttributes
0x1800816e0  mov     [rsp+460h+hTemplateFile], r14; hTemplateFile
0x1800816e5  mov     [rsp+460h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1800816ed  mov     edx, 80000000h; dwDesiredAccess
0x1800816f2  mov     rcx, rsi; lpFileName
0x1800816f5  mov     [rsp+460h+dwCreationDisposition], 3; dwCreationDisposition
0x1800816fd  lea     r8d, [r9+1]; dwShareMode
0x180081701  call    cs:__imp_CreateFileW
0x180081707  mov     [rbp+360h+var_3E0], rax
0x18008170b  mov     rbx, rax
0x18008170e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180081712  jz      short loc_18008178D
0x180081714  mov     rcx, rax; hFile
0x180081717  call    cs:__imp_GetFileType
0x18008171d  add     eax, 0FFFFFFFEh
0x180081720  cmp     eax, 1
0x180081723  ja      short loc_18008178D
0x180081725  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18008172c  jz      short loc_180081771
0x18008172e  mov     [rsp+460h+var_408], r14; void *
0x180081733  lea     rax, aNull; "(NULL)"
0x18008173a  mov     [rsp+460h+var_410], r14d; unsigned int
0x18008173f  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x180081746  mov     [rsp+460h+var_418], rax; unsigned __int16 *
0x18008174b  xor     edx, edx; unsigned __int16
0x18008174d  mov     [rsp+460h+var_420], rax; unsigned __int16 *
0x180081752  xor     r8d, r8d; int
0x180081755  mov     [rsp+460h+var_428], rax; unsigned __int16 *
0x18008175a  mov     [rsp+460h+hTemplateFile], rax; unsigned __int16 *
0x18008175f  mov     qword ptr [rsp+460h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x180081764  lea     ecx, [rdx+9]; int
0x180081767  mov     qword ptr [rsp+460h+dwCreationDisposition], rsi; unsigned __int16 *
0x18008176c  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180081771  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180081775  lea     rcx, [rbp+360h+var_3E0]
0x180081779  call    ??4CHandle@@QEAAXPEAX@Z; CHandle::operator=(void *)
0x18008177e  mov     ecx, 6Eh ; 'n'; dwErrCode
0x180081783  call    cs:__imp_SetLastError
0x180081789  mov     rbx, [rbp+360h+var_3E0]
0x18008178d  call    cs:__imp_GetLastError
0x180081793  test    edi, edi
0x180081795  jz      short loc_18008179C
0x180081797  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x18008179c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800817a0  jz      loc_180081A13
0x1800817a6  mov     edi, 4Ch ; 'L'
0x1800817ab  lea     rcx, [rbp+360h+Buffer]; void *
0x1800817af  mov     r8d, edi; Size
0x1800817b2  xor     edx, edx; Val
0x1800817b4  call    memset_0
0x1800817b9  lea     r9, [rsp+460h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800817be  mov     [rsp+460h+var_3E8], r14d
0x1800817c3  mov     r8d, edi; nNumberOfBytesToRead
0x1800817c6  mov     [rsp+460h+NumberOfBytesRead], r14d
0x1800817cb  lea     rdx, [rbp+360h+Buffer]; lpBuffer
0x1800817cf  mov     qword ptr [rsp+460h+dwCreationDisposition], r14; lpOverlapped
0x1800817d4  mov     rcx, rbx; hFile
0x1800817d7  call    cs:__imp_ReadFile
0x1800817dd  test    eax, eax
0x1800817df  jz      loc_180081A05
0x1800817e5  cmp     [rsp+460h+NumberOfBytesRead], edi
0x1800817e9  jnz     loc_180081A05
0x1800817ef  mov     edi, 1
0x1800817f4  test    byte ptr [rbp+360h+var_3AC], dil
0x1800817f8  jz      short loc_180081843
0x1800817fa  lea     r9, [rsp+460h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800817ff  mov     [rsp+460h+var_3FC], r14w
0x180081805  lea     r8d, [rdi+1]; nNumberOfBytesToRead
0x180081809  mov     qword ptr [rsp+460h+dwCreationDisposition], r14; lpOverlapped
0x18008180e  lea     rdx, [rsp+460h+var_3FC]; lpBuffer
0x180081813  mov     rcx, rbx; hFile
0x180081816  call    cs:__imp_ReadFile
0x18008181c  test    eax, eax
0x18008181e  jz      loc_180081A13
0x180081824  cmp     [rsp+460h+NumberOfBytesRead], 2
0x180081829  jnz     loc_180081A13
0x18008182f  movzx   edx, [rsp+460h+var_3FC]; lDistanceToMove
0x180081834  mov     r9d, edi; dwMoveMethod
0x180081837  xor     r8d, r8d; lpDistanceToMoveHigh
0x18008183a  mov     rcx, rbx; hFile
0x18008183d  call    cs:__imp_SetFilePointer
0x180081843  test    byte ptr [rbp+360h+var_3AC], 2
0x180081847  jz      short loc_180081899
0x180081849  lea     r9, [rsp+460h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18008184e  mov     qword ptr [rsp+460h+dwCreationDisposition], r14; lpOverlapped
0x180081853  mov     r8d, 4; nNumberOfBytesToRead
0x180081859  lea     rdx, [rsp+460h+var_3E8]; lpBuffer
0x18008185e  mov     rcx, rbx; hFile
0x180081861  call    cs:__imp_ReadFile
0x180081867  test    eax, eax
0x180081869  jz      loc_180081A13
0x18008186f  cmp     [rsp+460h+NumberOfBytesRead], 4
0x180081874  jnz     loc_180081A13
0x18008187a  mov     edx, [rsp+460h+var_3E8]
0x18008187e  cmp     edx, 4
0x180081881  jb      short loc_180081899
0x180081883  add     edx, 0FFFFFFFCh; lDistanceToMove
0x180081886  mov     r9d, edi; dwMoveMethod
0x180081889  xor     r8d, r8d; lpDistanceToMoveHigh
0x18008188c  mov     [rsp+460h+var_3E8], edx
0x180081890  mov     rcx, rbx; hFile
0x180081893  call    cs:__imp_SetFilePointer
0x180081899  mov     esi, [rbp+360h+var_3AC]
0x18008189c  mov     edi, r14d
0x18008189f  and     esi, 80h
0x1800818a5  movsxd  rax, edi
0x1800818a8  lea     rcx, qword_1802A7800
0x1800818af  mov     ecx, [rcx+rax*4]
0x1800818b2  test    ecx, ecx
0x1800818b4  jz      short loc_18008191A
0x1800818b6  test    [rbp+360h+var_3AC], ecx
0x1800818b9  jz      short loc_180081916
0x1800818bb  lea     r9, [rsp+460h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800818c0  mov     [rsp+460h+var_3FC], r14w
0x1800818c6  mov     r8d, 2; nNumberOfBytesToRead
0x1800818cc  mov     qword ptr [rsp+460h+dwCreationDisposition], r14; lpOverlapped
0x1800818d1  lea     rdx, [rsp+460h+var_3FC]; lpBuffer
0x1800818d6  mov     rcx, rbx; hFile
0x1800818d9  call    cs:__imp_ReadFile
0x1800818df  test    eax, eax
0x1800818e1  jz      loc_180081A13
0x1800818e7  cmp     [rsp+460h+NumberOfBytesRead], 2
0x1800818ec  jnz     loc_180081A13
0x1800818f2  mov     eax, esi
0x1800818f4  mov     r9d, 1; dwMoveMethod
0x1800818fa  neg     eax
0x1800818fc  mov     rcx, rbx; hFile
0x1800818ff  movzx   eax, [rsp+460h+var_3FC]
0x180081904  sbb     edx, edx
0x180081906  xor     r8d, r8d; lpDistanceToMoveHigh
0x180081909  neg     edx
0x18008190b  inc     edx
0x18008190d  imul    edx, eax; lDistanceToMove
0x180081910  call    cs:__imp_SetFilePointer
0x180081916  inc     edi
0x180081918  jmp     short loc_1800818A5
0x18008191a  xor     edx, edx; Val
0x18008191c  lea     rcx, [rbp+360h+var_370]; void *
0x180081920  mov     r8d, 314h; Size
0x180081926  call    memset_0
0x18008192b  lea     r9, [rsp+460h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180081930  mov     [rbp+360h+var_3D0], r14
0x180081934  mov     r8d, 8; nNumberOfBytesToRead
0x18008193a  mov     qword ptr [rsp+460h+dwCreationDisposition], r14; lpOverlapped
0x18008193f  lea     rdx, [rbp+360h+var_3D0]; lpBuffer
0x180081943  mov     rcx, rbx; hFile
0x180081946  call    cs:__imp_ReadFile
0x18008194c  test    eax, eax
0x18008194e  jz      short loc_180081983
0x180081950  cmp     [rsp+460h+NumberOfBytesRead], 8
0x180081955  jnz     short loc_180081983
0x180081957  cmp     dword ptr [rbp+360h+var_3D0+4], 0A0000006h
0x18008195e  jz      short loc_1800819AA
0x180081960  mov     rdx, [rbp+360h+var_3D0]
0x180081964  cmp     edx, 8
0x180081967  jbe     short loc_180081983
0x180081969  add     edx, 0FFFFFFF8h; lDistanceToMove
0x18008196c  mov     r9d, 1; dwMoveMethod
0x180081972  xor     r8d, r8d; lpDistanceToMoveHigh
0x180081975  mov     rcx, rbx; hFile
0x180081978  call    cs:__imp_SetFilePointer
0x18008197e  cmp     eax, 0FFFFFFFFh
0x180081981  jnz     short loc_18008192B
0x180081983  mov     ebx, r14d
  ... truncated ...
```
