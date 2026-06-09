# CActiveScriptEngine::Init(_GUID,ushort const *,ulong,CHitObj *,CTemplate *,ulong)

- ea: `0x180011970`
- end: `0x180011fcb`
- name: `?Init@CActiveScriptEngine@@QEAAJU_GUID@@PEBGKPEAVCHitObj@@PEAVCTemplate@@K@Z`
- size: `1627`
- prototype: `__int64 __fastcall(CActiveScriptEngine *this, struct _GUID *, const unsigned __int16 *, int, struct CHitObj *, struct CTemplate *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180008470`

## callees

- `0x18000ed80`
- `0x180011560`
- `0x180011970`
- `0x180011fe0`
- `0x180012060`
- `0x180012110`
- `0x18001e7a0`
- `0x18004197c`
- `0x180043218`
- `0x180064010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180011b1d`
- `msvcrt!wcscpy_s` at `0x180011b1d`
- `ole32!CoInitialize` at `0x180011a8f`
- `ole32!CoInitialize` at `0x180011a8f`
- `ole32!CoCreateInstance` at `0x180011a59`
- `ole32!CoCreateInstance` at `0x180011a59`
- `KERNEL32!HeapAlloc` at `0x180011af3`
- `KERNEL32!HeapAlloc` at `0x180011af3`

## string_xrefs

- `0x180011f83`: `IHostInfoUpdate::Release()`

## pseudocode

```c
__int64 __fastcall CActiveScriptEngine::Init(
        CActiveScriptEngine *this,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        int a4,
        struct CHitObj *a5,
        struct CTemplate *a6,
        unsigned int a7)
{
  _DWORD *v9; // r15
  int v11; // r12d
  CIsapiReqInfo *v12; // rcx
  unsigned int InstanceId; // eax
  void (*v14)(void); // rax
  HRESULT Instance; // eax
  HRESULT ASP; // ebx
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned __int64 v19; // rbx
  wchar_t *v20; // rax
  SIZE_T v21; // rax
  char *v22; // rdx
  unsigned int i; // ebx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  _QWORD *v27; // r14
  char *v28; // rdi
  _QWORD *v29; // [rsp+38h] [rbp-A0h]
  __int64 v31; // [rsp+58h] [rbp-80h] BYREF
  char *v32; // [rsp+60h] [rbp-78h]
  __int128 v33; // [rsp+68h] [rbp-70h] BYREF
  __int64 v34; // [rsp+78h] [rbp-60h]
  __int128 v35; // [rsp+80h] [rbp-58h] BYREF
  __int64 v36; // [rsp+90h] [rbp-48h]

  v9 = (_DWORD *)((char *)this + 276);
  if ( (*((_BYTE *)this + 276) & 1) != 0 )
    return 1247;
  v11 = 0;
  *((_DWORD *)this + 55) = a4;
  *(struct _GUID *)((char *)this + 204) = *a2;
  *((_QWORD *)this + 7) = a5;
  *((_DWORD *)this + 68) = a7;
  v12 = (CIsapiReqInfo *)*((_QWORD *)a5 + 8);
  if ( v12 )
    InstanceId = CIsapiReqInfo::QueryInstanceId(v12);
  else
    InstanceId = 0;
  *((_DWORD *)this + 18) = InstanceId;
  v32 = (char *)this + 264;
  *((_QWORD *)this + 33) = a6;
  v14 = *(void (**)(void))(*((_QWORD *)a6 + 3) + 8LL);
  if ( (char *)v14 == (char *)CTemplate::AddRef )
    CTemplate::AddRef((struct CTemplate *)((char *)a6 + 24));
  else
    v14();
  *((_QWORD *)this + 35) = 0;
  v29 = (_QWORD *)((char *)this + 224);
  while ( 1 )
  {
    Instance = CoCreateInstance(a2, 0, 1u, &IID_IActiveScript, (LPVOID *)this + 28);
    ASP = Instance;
    if ( Instance >= 0 )
      break;
    if ( Instance == -2147221008 && !v11 )
    {
      v11 = 1;
      MSG_Error(0x6Cu);
      ASP = CoInitialize(0);
      if ( ASP >= 0 )
        continue;
    }
    goto LABEL_37;
  }
  v17 = -1;
  do
    ++v17;
  while ( a3[v17] );
  v18 = (unsigned int)(v17 + 1);
  v19 = (unsigned int)v18;
  if ( (unsigned __int64)(2 * v18) > 0x80 )
  {
    v21 = 2LL * (unsigned int)v18;
    if ( !is_mul_ok(v19, 2u) )
      v21 = -1;
    v20 = (wchar_t *)HeapAlloc(g_hDenaliHeap, 0, v21);
    *((_QWORD *)this + 8) = v20;
    if ( !v20 )
    {
      ASP = -2147024882;
      goto LABEL_38;
    }
    *v9 |= 0x20u;
  }
  else
  {
    v20 = (wchar_t *)((char *)this + 76);
    *((_QWORD *)this + 8) = (char *)this + 76;
    *v9 &= ~0x20u;
  }
  wcscpy_s(v20, v19, a3);
  v22 = (char *)this + 8;
  if ( !this )
    v22 = 0;
  ASP = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v29 + 24LL))(*v29, v22);
  if ( ASP >= 0 )
  {
    v31 = 0;
    if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v29)(*v29, &IID_IActiveScriptProperty, &v31) >= 0 )
    {
      v33 = 0;
      v34 = 0;
      v35 = 0;
      v36 = 0;
      LOWORD(v35) = 3;
      LOWORD(v33) = 11;
      WORD4(v33) = -1;
      for ( i = 0; i < 0x11; ++i )
      {
        DWORD2(v35) = *((_DWORD *)qword_18006B160 + (int)i);
        (*(void (__fastcall **)(__int64, __int64, __int128 *, __int128 *))(*(_QWORD *)v31 + 32LL))(
          v31,
          4097,
          &v35,
          &v33);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    ASP = CActiveScriptEngine::GetASP(this);
    if ( ASP >= 0 )
    {
      CActiveScriptEngine::GetASTI(this);
      ASP = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 24LL))(*((_QWORD *)this + 30));
      if ( ASP < 0 )
        goto LABEL_38;
      ASP = CActiveScriptEngine::GetIDisp(this);
      if ( ASP >= 0 )
      {
        ASP = CActiveScriptEngine::GetIHostInfoUpdate(this);
        if ( ASP >= 0 )
          *v9 |= 1u;
      }
    }
LABEL_37:
    if ( ASP >= 0 )
      return (unsigned int)ASP;
  }
LABEL_38:
  if ( *v29 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v29 + 16LL))(*v29);
    *v29 = 0;
  }
  v24 = *((_QWORD *)this + 30);
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    *((_QWORD *)this + 30) = 0;
  }
  v25 = *((_QWORD *)this + 6);
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    *((_QWORD *)this + 6) = 0;
  }
  v26 = *((_QWORD *)this + 29);
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    *((_QWORD *)this + 29) = 0;
  }
  v27 = v32;
  if ( *(_QWORD *)v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v32 + 24LL) + 16LL))(*(_QWORD *)v32 + 24LL);
    *v27 = 0;
  }
  v28 = (char *)this + 248;
  v32 = v28;
  if ( *(_QWORD *)v28 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 16LL))(*(_QWORD *)v28);
    *(_QWORD *)v28 = 0;
  }
  return (unsigned int)ASP;
}

```

## disassembly

```asm
0x180011970  push    rbx
0x180011972  push    rsi
0x180011973  push    rdi
0x180011974  push    r12
0x180011976  push    r13
0x180011978  push    r14
0x18001197a  push    r15
0x18001197c  sub     rsp, 0A0h
0x180011983  mov     r13, r8
0x180011986  mov     [rsp+0D8h+rclsid], rdx
0x18001198b  mov     rdi, rcx
0x18001198e  mov     [rsp+0D8h+var_98], rcx
0x180011993  mov     rcx, [rsp+0D8h+arg_20]
0x18001199b  lea     r15, [rdi+114h]
0x1800119a2  test    byte ptr [r15], 1
0x1800119a6  jz      short loc_1800119B2
0x1800119a8  mov     eax, 4DFh
0x1800119ad  jmp     loc_180011FB8
0x1800119b2  xor     esi, esi
0x1800119b4  mov     r12d, esi
0x1800119b7  mov     [rdi+0DCh], r9d
0x1800119be  movups  xmm0, xmmword ptr [rdx]
0x1800119c1  movups  xmmword ptr [rdi+0CCh], xmm0
0x1800119c8  mov     [rdi+38h], rcx
0x1800119cc  mov     eax, [rsp+0D8h+arg_30]
0x1800119d3  mov     [rdi+110h], eax
0x1800119d9  mov     rcx, [rcx+40h]; this
0x1800119dd  test    rcx, rcx
0x1800119e0  jz      short loc_1800119E9
0x1800119e2  call    ?QueryInstanceId@CIsapiReqInfo@@QEAAKXZ; CIsapiReqInfo::QueryInstanceId(void)
0x1800119e7  jmp     short loc_1800119EB
0x1800119e9  mov     eax, esi
0x1800119eb  mov     [rdi+48h], eax
0x1800119ee  lea     r14, [rdi+108h]
0x1800119f5  mov     [rsp+0D8h+var_78], r14
0x1800119fa  mov     rax, [rsp+0D8h+arg_28]
0x180011a02  mov     [r14], rax
0x180011a05  lea     rcx, [rax+18h]; this
0x180011a09  mov     rax, [rcx]
0x180011a0c  mov     rax, [rax+8]
0x180011a10  lea     rdx, ?AddRef@CTemplate@@UEAAKXZ; CTemplate::AddRef(void)
0x180011a17  cmp     rax, rdx
0x180011a1a  jnz     short loc_180011A23
0x180011a1c  call    ?AddRef@CTemplate@@UEAAKXZ; CTemplate::AddRef(void)
0x180011a21  jmp     short loc_180011A28
0x180011a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a28  mov     [rdi+118h], rsi
0x180011a2f  lea     r14, [rdi+0E0h]
0x180011a36  mov     [rsp+0D8h+var_A0], r14
0x180011a3b  nop     dword ptr [rax+rax+00h]
0x180011a40  mov     [rsp+0D8h+ppv], r14; ppv
0x180011a45  lea     r9, IID_IActiveScript; riid
0x180011a4c  xor     edx, edx; pUnkOuter
0x180011a4e  mov     r8d, 1; dwClsContext
0x180011a54  mov     rcx, [rsp+0D8h+rclsid]; rclsid
0x180011a59  call    cs:__imp_CoCreateInstance
0x180011a5f  mov     ebx, eax
0x180011a61  mov     [rsp+0D8h+var_A8], eax
0x180011a65  test    eax, eax
0x180011a67  jns     short loc_180011AA4
0x180011a69  cmp     eax, 800401F0h
0x180011a6e  jnz     loc_180011DA4
0x180011a74  test    r12d, r12d
0x180011a77  jnz     loc_180011DA4
0x180011a7d  mov     ecx, 6Ch ; 'l'; uID
0x180011a82  mov     r12d, 1
0x180011a88  call    ?MSG_Error@@YAXI@Z; MSG_Error(uint)
0x180011a8d  xor     ecx, ecx; pvReserved
0x180011a8f  call    cs:__imp_CoInitialize
0x180011a95  mov     ebx, eax
0x180011a97  mov     [rsp+0D8h+var_A8], eax
0x180011a9b  test    eax, eax
0x180011a9d  jns     short loc_180011A40
0x180011a9f  jmp     loc_180011DA4
0x180011aa4  mov     [rsp+0D8h+rclsid], r15
0x180011aa9  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180011ab0  mov     rax, r14
0x180011ab3  inc     rax
0x180011ab6  cmp     [r13+rax*2+0], si
0x180011abc  jnz     short loc_180011AB3
0x180011abe  inc     eax
0x180011ac0  mov     ebx, eax
0x180011ac2  add     rax, rax
0x180011ac5  cmp     rax, 80h
0x180011acb  ja      short loc_180011ADB
0x180011acd  lea     rax, [rdi+4Ch]
0x180011ad1  mov     [rdi+40h], rax
0x180011ad5  and     dword ptr [r15], 0FFFFFFDFh
0x180011ad9  jmp     short loc_180011B14
0x180011adb  mov     eax, 2
0x180011ae0  mul     rbx
0x180011ae3  cmovb   rax, r14
0x180011ae7  mov     r8, rax; dwBytes
0x180011aea  xor     edx, edx; dwFlags
0x180011aec  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180011af3  call    cs:__imp_HeapAlloc
0x180011af9  mov     [rdi+40h], rax
0x180011afd  test    rax, rax
0x180011b00  jnz     short loc_180011B10
0x180011b02  mov     ebx, 8007000Eh
0x180011b07  mov     [rsp+0D8h+var_A8], ebx
0x180011b0b  jmp     loc_180011DAC
0x180011b10  or      dword ptr [r15], 20h
0x180011b14  mov     r8, r13; Source
0x180011b17  mov     rdx, rbx; SizeInWords
0x180011b1a  mov     rcx, rax; Destination
0x180011b1d  call    cs:__imp_wcscpy_s
0x180011b23  nop
0x180011b24  mov     rax, [rsp+0D8h+var_A0]
0x180011b29  mov     rcx, [rax]
0x180011b2c  mov     rax, [rcx]
0x180011b2f  lea     rdx, [rdi+8]
0x180011b33  test    rdi, rdi
0x180011b36  cmovz   rdx, rsi
0x180011b3a  mov     rax, [rax+18h]
0x180011b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b43  mov     ebx, eax
0x180011b45  mov     [rsp+0D8h+var_A8], eax
0x180011b49  jmp     short loc_180011B93
0x180011b4b  mov     ebx, eax
0x180011b4d  lea     rax, aCactivescripte_14; "CActiveScriptEngine::Init()"
0x180011b54  mov     [rsp+0D8h+var_B0], rax
0x180011b59  lea     rax, aIactivescriptS; "IActiveScript::SetScriptSite()"
0x180011b60  mov     [rsp+0D8h+ppv], rax
0x180011b65  mov     r9d, ebx
0x180011b68  mov     r8d, 1; int
0x180011b6e  mov     rdi, [rsp+0D8h+var_98]
0x180011b73  mov     rdx, [rdi+38h]; struct CHitObj *
0x180011b77  mov     ecx, 3F4h; unsigned int
0x180011b7c  call    ?HandleErrorMissingFilename@@YAXIPEAVCHitObj@@HZZ; HandleErrorMissingFilename(uint,CHitObj *,int,...)
0x180011b81  mov     [rsp+0D8h+var_A8], ebx
0x180011b85  xor     esi, esi
0x180011b87  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180011b8e  mov     r15, [rsp+0D8h+rclsid]
0x180011b93  test    ebx, ebx
0x180011b95  js      loc_180011DAC
0x180011b9b  mov     [rsp+0D8h+var_80], rsi
0x180011ba0  mov     rax, [rsp+0D8h+var_A0]
0x180011ba5  mov     rcx, [rax]
0x180011ba8  mov     rax, [rcx]
0x180011bab  lea     r8, [rsp+0D8h+var_80]
0x180011bb0  lea     rdx, IID_IActiveScriptProperty
0x180011bb7  mov     rax, [rax]
0x180011bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bbf  mov     ebx, eax
0x180011bc1  mov     [rsp+0D8h+var_A8], eax
0x180011bc5  jmp     short loc_180011C0F
0x180011bc7  mov     ebx, eax
0x180011bc9  lea     rax, aCactivescripte_14; "CActiveScriptEngine::Init()"
0x180011bd0  mov     [rsp+0D8h+var_B0], rax
0x180011bd5  lea     rax, aIactivescriptQ; "IActiveScript::QueryInterface()"
0x180011bdc  mov     [rsp+0D8h+ppv], rax
0x180011be1  mov     r9d, ebx
0x180011be4  mov     r8d, 1; int
0x180011bea  mov     rdi, [rsp+0D8h+var_98]
0x180011bef  mov     rdx, [rdi+38h]; struct CHitObj *
0x180011bf3  mov     ecx, 3F4h; unsigned int
0x180011bf8  call    ?HandleErrorMissingFilename@@YAXIPEAVCHitObj@@HZZ; HandleErrorMissingFilename(uint,CHitObj *,int,...)
0x180011bfd  mov     [rsp+0D8h+var_A8], ebx
0x180011c01  xor     esi, esi
0x180011c03  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180011c0a  mov     r15, [rsp+0D8h+rclsid]
0x180011c0f  test    ebx, ebx
0x180011c11  js      loc_180011CFD
0x180011c17  xorps   xmm0, xmm0
0x180011c1a  xor     eax, eax
0x180011c1c  movups  [rsp+0D8h+var_70], xmm0
0x180011c21  mov     [rsp+0D8h+var_60], rax
0x180011c26  xorps   xmm1, xmm1
0x180011c29  movups  [rsp+0D8h+var_58], xmm1
0x180011c31  mov     [rsp+0D8h+var_48], rax
0x180011c39  mov     eax, 3
0x180011c3e  mov     word ptr [rsp+0D8h+var_58], ax
0x180011c46  mov     eax, 0Bh
0x180011c4b  mov     word ptr [rsp+0D8h+var_70], ax
0x180011c50  mov     word ptr [rsp+0D8h+var_70+8], r14w
0x180011c56  mov     ebx, esi
0x180011c58  lea     r14, qword_18006B160
0x180011c5f  mov     [rsp+0D8h+var_88], ebx
0x180011c63  cmp     ebx, 11h
0x180011c66  jnb     loc_180011CEC
0x180011c6c  movsxd  rax, ebx
0x180011c6f  mov     eax, [r14+rax*4]
0x180011c73  mov     dword ptr [rsp+0D8h+var_58+8], eax
0x180011c7a  mov     rcx, [rsp+0D8h+var_80]
0x180011c7f  mov     rax, [rcx]
0x180011c82  lea     r9, [rsp+0D8h+var_70]
0x180011c87  lea     r8, [rsp+0D8h+var_58]
0x180011c8f  mov     edx, 1001h
0x180011c94  mov     rax, [rax+20h]
0x180011c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c9d  jmp     short loc_180011CE5
0x180011c9f  mov     r9d, eax
0x180011ca2  lea     rax, aCactivescripte_14; "CActiveScriptEngine::Init()"
0x180011ca9  mov     [rsp+0D8h+var_B0], rax
0x180011cae  lea     rax, aIactivescriptp_0; "IActiveScriptProperty::SetProperty"
0x180011cb5  mov     [rsp+0D8h+ppv], rax
0x180011cba  mov     r8d, 1; int
0x180011cc0  mov     rdi, [rsp+0D8h+var_98]
0x180011cc5  mov     rdx, [rdi+38h]; struct CHitObj *
0x180011cc9  mov     ecx, 3F4h; unsigned int
0x180011cce  call    ?HandleErrorMissingFilename@@YAXIPEAVCHitObj@@HZZ; HandleErrorMissingFilename(uint,CHitObj *,int,...)
0x180011cd3  xor     esi, esi
0x180011cd5  lea     r14, qword_18006B160
0x180011cdc  mov     ebx, [rsp+0D8h+var_88]
0x180011ce0  mov     r15, [rsp+0D8h+rclsid]
0x180011ce5  inc     ebx
0x180011ce7  jmp     loc_180011C5F
0x180011cec  mov     rcx, [rsp+0D8h+var_80]
0x180011cf1  mov     rax, [rcx]
0x180011cf4  mov     rax, [rax+10h]
0x180011cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cfd  mov     rcx, rdi; this
0x180011d00  call    ?GetASP@CActiveScriptEngine@@QEAAJXZ; CActiveScriptEngine::GetASP(void)
0x180011d05  mov     ebx, eax
0x180011d07  mov     [rsp+0D8h+var_A8], eax
0x180011d0b  test    eax, eax
0x180011d0d  js      loc_180011DA4
0x180011d13  mov     rcx, rdi; this
0x180011d16  call    ?GetASTI@CActiveScriptEngine@@QEAAJXZ; CActiveScriptEngine::GetASTI(void)
0x180011d1b  nop
0x180011d1c  mov     rcx, [rdi+0F0h]
0x180011d23  mov     rax, [rcx]
0x180011d26  mov     rax, [rax+18h]
0x180011d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d2f  mov     ebx, eax
0x180011d31  mov     [rsp+0D8h+var_A8], eax
0x180011d35  jmp     short loc_180011D78
0x180011d37  mov     ebx, eax
0x180011d39  lea     rax, aCactivescripte_14; "CActiveScriptEngine::Init()"
0x180011d40  mov     [rsp+0D8h+var_B0], rax
0x180011d45  lea     rax, aIactivescriptp_1; "IActiveScriptParse::InitNew()"
0x180011d4c  mov     [rsp+0D8h+ppv], rax
0x180011d51  mov     r9d, ebx
0x180011d54  mov     r8d, 1; int
0x180011d5a  mov     rdi, [rsp+0D8h+var_98]
0x180011d5f  mov     rdx, [rdi+38h]; struct CHitObj *
0x180011d63  mov     ecx, 3F4h; unsigned int
0x180011d68  call    ?HandleErrorMissingFilename@@YAXIPEAVCHitObj@@HZZ; HandleErrorMissingFilename(uint,CHitObj *,int,...)
0x180011d6d  mov     [rsp+0D8h+var_A8], ebx
0x180011d71  xor     esi, esi
0x180011d73  mov     r15, [rsp+0D8h+rclsid]
0x180011d78  test    ebx, ebx
0x180011d7a  js      short loc_180011DAC
0x180011d7c  mov     rcx, rdi; this
0x180011d7f  call    ?GetIDisp@CActiveScriptEngine@@QEAAJXZ; CActiveScriptEngine::GetIDisp(void)
0x180011d84  mov     ebx, eax
0x180011d86  mov     [rsp+0D8h+var_A8], eax
0x180011d8a  test    eax, eax
0x180011d8c  js      short loc_180011DA4
0x180011d8e  mov     rcx, rdi; this
0x180011d91  call    ?GetIHostInfoUpdate@CActiveScriptEngine@@QEAAJXZ; CActiveScriptEngine::GetIHostInfoUpdate(void)
0x180011d96  mov     ebx, eax
0x180011d98  mov     [rsp+0D8h+var_A8], eax
0x180011d9c  test    eax, eax
0x180011d9e  js      short loc_180011DA4
0x180011da0  or      dword ptr [r15], 1
0x180011da4  test    ebx, ebx
0x180011da6  jns     loc_180011FB6
0x180011dac  mov     rax, [rsp+0D8h+var_A0]
0x180011db1  mov     rcx, [rax]
0x180011db4  test    rcx, rcx
0x180011db7  jz      short loc_180011E09
0x180011db9  mov     rax, [rcx]
0x180011dbc  mov     rax, [rax+10h]
0x180011dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dc5  jmp     short loc_180011E01
0x180011dc7  mov     r9d, eax
0x180011dca  lea     rax, aCactivescripte_14; "CActiveScriptEngine::Init()"
0x180011dd1  mov     [rsp+0D8h+var_B0], rax
0x180011dd6  lea     rax, aIactivescriptR; "IActiveScript::Release()"
0x180011ddd  mov     [rsp+0D8h+ppv], rax
0x180011de2  mov     r8d, 1; int
0x180011de8  mov     rdi, [rsp+0D8h+var_98]
0x180011ded  mov     rdx, [rdi+38h]; struct CHitObj *
0x180011df1  mov     ecx, 3F4h; unsigned int
0x180011df6  call    ?HandleErrorMissingFilename@@YAXIPEAVCHitObj@@HZZ; HandleErrorMissingFilename(uint,CHitObj *,int,...)
0x180011dfb  xor     esi, esi
0x180011dfd  mov     ebx, [rsp+0D8h+var_A8]
0x180011e01  mov     rax, [rsp+0D8h+var_A0]
0x180011e06  mov     [rax], rsi
0x180011e09  lea     r14, [rdi+0F0h]
0x180011e10  mov     [rsp+0D8h+var_A0], r14
0x180011e15  mov     rcx, [r14]
0x180011e18  test    rcx, rcx
0x180011e1b  jz      short loc_180011E6D
0x180011e1d  mov     rax, [rcx]
0x180011e20  mov     rax, [rax+10h]
0x180011e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e29  jmp     short loc_180011E6A
0x180011e2b  mov     r9d, eax
0x180011e2e  lea     rax, aCactivescripte_14; "CActiveScriptEngine::Init()"
0x180011e35  mov     [rsp+0D8h+var_B0], rax
0x180011e3a  lea     rax, aIactivescriptp_2; "IActiveScriptParse::Release()"
0x180011e41  mov     [rsp+0D8h+ppv], rax
0x180011e46  mov     r8d, 1; int
0x180011e4c  mov     rdi, [rsp+0D8h+var_98]
0x180011e51  mov     rdx, [rdi+38h]; struct CHitObj *
0x180011e55  mov     ecx, 3F4h; unsigned int
0x180011e5a  call    ?HandleErrorMissingFilename@@YAXIPEAVCHitObj@@HZZ; HandleErrorMissingFilename(uint,CHitObj *,int,...)
  ... truncated ...
```
