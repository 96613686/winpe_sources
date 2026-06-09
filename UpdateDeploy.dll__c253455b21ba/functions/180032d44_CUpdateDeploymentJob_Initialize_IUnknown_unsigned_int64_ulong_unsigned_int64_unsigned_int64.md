# CUpdateDeploymentJob::Initialize(IUnknown *,unsigned __int64,ulong,unsigned __int64,unsigned __int64)

- ea: `0x180032d44`
- end: `0x1800330b1`
- name: `?Initialize@CUpdateDeploymentJob@@QEAAJPEAUIUnknown@@_KK_K1@Z`
- size: `877`
- prototype: `__int64 __usercall@<rax>(CUpdateDeploymentJob *__hidden this@<rcx>, struct IUnknown *@<rdx>, unsigned __int64@<r8>, unsigned int@<r9d>, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x18001cd60`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000dce4`
- `0x1800110fc`
- `0x180011b44`
- `0x1800175c4`
- `0x18003291c`
- `0x180032a9c`
- `0x180032d44`
- `0x180038914`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032f94`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180032f94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032fa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032fa9`

## string_xrefs

- `0x180032d87`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180032ded`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180032eea`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180032fc3`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180033035`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`

## pseudocode

```c
__int64 __fastcall CUpdateDeploymentJob::Initialize(
        CUpdateDeploymentJob *this,
        struct IUnknown *a2,
        __int64 a3,
        int a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 *v13; // r14
  __int64 v14; // rcx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rsi
  int v16; // esi
  __int64 v17; // rdx
  __int64 v18; // rcx
  HRESULT (__stdcall *v19)(IUnknown *, const IID *const, void **); // rbp
  __int64 v20; // rcx
  HRESULT (__stdcall *v21)(IUnknown *, const IID *const, void **); // rbp
  __int64 v22; // rcx
  HRESULT (__stdcall *v23)(IUnknown *, const IID *const, void **); // rbp
  int LastError; // edi
  __int64 v25; // rdx
  __int64 v26; // rsi
  void *v27; // rcx
  __int64 (__fastcall *v28)(__int64, char *); // rbp
  HANDLE EventW; // rax
  const char *v30; // r9
  void *v31; // rcx
  HANDLE v32; // rdi
  const struct _GUID *v33; // rdi
  int UDPPrivateNamespace; // eax
  __int64 v35; // rax
  int v36; // [rsp+20h] [rbp-88h]
  _BYTE v37[80]; // [rsp+40h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  if ( !a2 )
  {
    v10 = -2147467261;
    v11 = 4495;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)v10,
      v36);
    return v10;
  }
  v13 = (__int64 *)((char *)this + 704);
  v14 = *((_QWORD *)this + 88);
  QueryInterface = a2->lpVtbl->QueryInterface;
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *v13 = 0;
  }
  v16 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))QueryInterface)(
          a2,
          &GUID_4340b49e_6c13_4d9a_836a_ff2430fdfcb2,
          v13);
  if ( v16 < 0 )
  {
    v17 = 4498;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)v16,
      v36);
    return (unsigned int)v16;
  }
  v18 = *((_QWORD *)this + 89);
  v19 = a2->lpVtbl->QueryInterface;
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    *((_QWORD *)this + 89) = 0;
  }
  v16 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))v19)(
          a2,
          &GUID_6e0d3386_7aa6_415f_bda9_82024a16b101,
          (char *)this + 712);
  if ( v16 < 0 )
  {
    v17 = 4500;
    goto LABEL_8;
  }
  v20 = *((_QWORD *)this + 90);
  v21 = a2->lpVtbl->QueryInterface;
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    *((_QWORD *)this + 90) = 0;
  }
  v16 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))v21)(
          a2,
          &GUID_982b27e3_63e9_4514_a328_82c364342a77,
          (char *)this + 720);
  if ( v16 < 0 )
  {
    v17 = 4502;
    goto LABEL_8;
  }
  v22 = *((_QWORD *)this + 91);
  v23 = a2->lpVtbl->QueryInterface;
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    *((_QWORD *)this + 91) = 0;
  }
  LastError = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))v23)(
                a2,
                &GUID_8c3183e6_a10b_42bc_9768_909717dec26b,
                (char *)this + 728);
  if ( LastError < 0 )
  {
    v25 = 4504;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)LastError,
      v36);
    return (unsigned int)LastError;
  }
  v26 = *v13;
  *((_QWORD *)this + 101) = a5;
  *((_QWORD *)this + 102) = a6;
  *((_QWORD *)this + 99) = a3;
  *((_DWORD *)this + 200) = a4;
  v27 = (void *)*((_QWORD *)this + 85);
  v28 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 24LL);
  if ( v27 )
  {
    SusFree(v27);
    *((_QWORD *)this + 85) = 0;
  }
  LastError = v28(v26, (char *)this + 680);
  if ( LastError < 0 )
  {
    v25 = 4511;
    goto LABEL_21;
  }
  LastError = CUHHandlerManager::Init((CUpdateDeploymentJob *)((char *)this + 48));
  if ( LastError < 0 )
  {
    v25 = 4512;
    goto LABEL_21;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  v31 = (void *)*((_QWORD *)this + 98);
  v32 = EventW;
  if ( v31 )
    CloseHandle(v31);
  *((_QWORD *)this + 98) = v32;
  if ( !v32 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x115D,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
                  v30);
    if ( LastError < 0 )
    {
      v25 = 4513;
      goto LABEL_21;
    }
  }
  LastError = CUpdateDeploymentJob::CreateDeploymentWorker((struct _GUID *)this);
  if ( LastError < 0 )
  {
    v25 = 4514;
    goto LABEL_21;
  }
  LastError = CUpdateDeploymentJob::CreateCallbackWorker(this);
  if ( LastError < 0 )
  {
    v25 = 4515;
    goto LABEL_21;
  }
  v33 = (const struct _GUID *)((char *)this + 16);
  UDPPrivateNamespace = mutex::CreateUDPPrivateNamespace((const UUID *)this + 1, (_QWORD *)this + 123);
  v10 = UDPPrivateNamespace;
  if ( UDPPrivateNamespace < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x117B,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)UDPPrivateNamespace,
      v36);
    v11 = 4516;
    goto LABEL_3;
  }
  v35 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v37, v33);
  WUTrace(0, 0, 0x1000000, 4, 0, L"Deployment job Id %ws : Initialized successfully.", v35);
  return 0;
}

```

## disassembly

```asm
0x180032d44  mov     rax, rsp
0x180032d47  mov     [rax+8], rbx
0x180032d4b  mov     [rax+10h], rbp
0x180032d4f  mov     [rax+18h], rsi
0x180032d53  mov     [rax+20h], rdi
0x180032d57  push    r12
0x180032d59  push    r14
0x180032d5b  push    r15
0x180032d5d  sub     rsp, 90h
0x180032d64  mov     r15d, r9d
0x180032d67  mov     r12, r8
0x180032d6a  mov     rdi, rdx
0x180032d6d  mov     rbx, rcx
0x180032d70  test    rdx, rdx
0x180032d73  jnz     short loc_180032D9D
0x180032d75  mov     ebx, 80004003h
0x180032d7a  mov     edx, 118Fh; void *
0x180032d7f  mov     rcx, [rsp+0A8h]; this
0x180032d87  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180032d8e  mov     r9d, ebx; char *
0x180032d91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032d96  mov     eax, ebx
0x180032d98  jmp     loc_18003308F
0x180032d9d  mov     rax, [rdx]
0x180032da0  lea     r14, [rcx+2C0h]
0x180032da7  mov     rcx, [r14]
0x180032daa  mov     rsi, [rax]
0x180032dad  test    rcx, rcx
0x180032db0  jz      short loc_180032DC5
0x180032db2  mov     rdx, [rcx]
0x180032db5  mov     rax, [rdx+10h]
0x180032db9  call    _guard_dispatch_icall
0x180032dbe  mov     qword ptr [r14], 0
0x180032dc5  mov     r8, r14
0x180032dc8  lea     rdx, _GUID_4340b49e_6c13_4d9a_836a_ff2430fdfcb2
0x180032dcf  mov     rcx, rdi
0x180032dd2  mov     rax, rsi
0x180032dd5  call    _guard_dispatch_icall
0x180032dda  mov     esi, eax
0x180032ddc  test    eax, eax
0x180032dde  jns     short loc_180032E03
0x180032de0  mov     edx, 1192h; void *
0x180032de5  mov     rcx, [rsp+0A8h]; this
0x180032ded  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180032df4  mov     r9d, esi; char *
0x180032df7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032dfc  mov     eax, esi
0x180032dfe  jmp     loc_18003308F
0x180032e03  mov     rax, [rdi]
0x180032e06  lea     rsi, [rbx+2C8h]
0x180032e0d  mov     rcx, [rsi]
0x180032e10  mov     rbp, [rax]
0x180032e13  test    rcx, rcx
0x180032e16  jz      short loc_180032E2B
0x180032e18  mov     rdx, [rcx]
0x180032e1b  mov     rax, [rdx+10h]
0x180032e1f  call    _guard_dispatch_icall
0x180032e24  mov     qword ptr [rsi], 0
0x180032e2b  mov     r8, rsi
0x180032e2e  lea     rdx, _GUID_6e0d3386_7aa6_415f_bda9_82024a16b101
0x180032e35  mov     rcx, rdi
0x180032e38  mov     rax, rbp
0x180032e3b  call    _guard_dispatch_icall
0x180032e40  mov     esi, eax
0x180032e42  test    eax, eax
0x180032e44  jns     short loc_180032E4D
0x180032e46  mov     edx, 1194h
0x180032e4b  jmp     short loc_180032DE5
0x180032e4d  mov     rax, [rdi]
0x180032e50  lea     rsi, [rbx+2D0h]
0x180032e57  mov     rcx, [rsi]
0x180032e5a  mov     rbp, [rax]
0x180032e5d  test    rcx, rcx
0x180032e60  jz      short loc_180032E75
0x180032e62  mov     rdx, [rcx]
0x180032e65  mov     rax, [rdx+10h]
0x180032e69  call    _guard_dispatch_icall
0x180032e6e  mov     qword ptr [rsi], 0
0x180032e75  mov     r8, rsi
0x180032e78  lea     rdx, _GUID_982b27e3_63e9_4514_a328_82c364342a77
0x180032e7f  mov     rcx, rdi
0x180032e82  mov     rax, rbp
0x180032e85  call    _guard_dispatch_icall
0x180032e8a  mov     esi, eax
0x180032e8c  test    eax, eax
0x180032e8e  jns     short loc_180032E9A
0x180032e90  mov     edx, 1196h
0x180032e95  jmp     loc_180032DE5
0x180032e9a  mov     rax, [rdi]
0x180032e9d  lea     rsi, [rbx+2D8h]
0x180032ea4  mov     rcx, [rsi]
0x180032ea7  mov     rbp, [rax]
0x180032eaa  test    rcx, rcx
0x180032ead  jz      short loc_180032EC2
0x180032eaf  mov     rdx, [rcx]
0x180032eb2  mov     rax, [rdx+10h]
0x180032eb6  call    _guard_dispatch_icall
0x180032ebb  mov     qword ptr [rsi], 0
0x180032ec2  mov     r8, rsi
0x180032ec5  lea     rdx, _GUID_8c3183e6_a10b_42bc_9768_909717dec26b
0x180032ecc  mov     rcx, rdi
0x180032ecf  mov     rax, rbp
0x180032ed2  call    _guard_dispatch_icall
0x180032ed7  mov     edi, eax
0x180032ed9  test    eax, eax
0x180032edb  jns     short loc_180032F00
0x180032edd  mov     edx, 1198h; void *
0x180032ee2  mov     rcx, [rsp+0A8h]; this
0x180032eea  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180032ef1  mov     r9d, edi; char *
0x180032ef4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032ef9  mov     eax, edi
0x180032efb  jmp     loc_18003308F
0x180032f00  mov     rax, [rsp+0A8h+arg_20]
0x180032f08  lea     rdi, [rbx+2A8h]
0x180032f0f  mov     rsi, [r14]
0x180032f12  mov     [rbx+328h], rax
0x180032f19  mov     rax, [rsp+0A8h+arg_28]
0x180032f21  mov     [rbx+330h], rax
0x180032f28  mov     [rbx+318h], r12
0x180032f2f  mov     [rbx+320h], r15d
0x180032f36  mov     rax, [rsi]
0x180032f39  mov     rcx, [rdi]; lpMem
0x180032f3c  mov     rbp, [rax+18h]
0x180032f40  test    rcx, rcx
0x180032f43  jz      short loc_180032F51
0x180032f45  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180032f4a  mov     qword ptr [rdi], 0
0x180032f51  mov     rdx, rdi
0x180032f54  mov     rcx, rsi
0x180032f57  mov     rax, rbp
0x180032f5a  call    _guard_dispatch_icall
0x180032f5f  mov     edi, eax
0x180032f61  test    eax, eax
0x180032f63  jns     short loc_180032F6F
0x180032f65  mov     edx, 119Fh
0x180032f6a  jmp     loc_180032EE2
0x180032f6f  lea     rcx, [rbx+30h]; this
0x180032f73  call    ?Init@CUHHandlerManager@@QEAAJXZ; CUHHandlerManager::Init(void)
0x180032f78  mov     edi, eax
0x180032f7a  test    eax, eax
0x180032f7c  jns     short loc_180032F88
0x180032f7e  mov     edx, 11A0h
0x180032f83  jmp     loc_180032EE2
0x180032f88  xor     r9d, r9d; lpName
0x180032f8b  xor     r8d, r8d; bInitialState
0x180032f8e  xor     ecx, ecx; lpEventAttributes
0x180032f90  lea     edx, [r9+1]; bManualReset
0x180032f94  call    cs:__imp_CreateEventW
0x180032f9a  mov     rcx, [rbx+310h]; hObject
0x180032fa1  mov     rdi, rax
0x180032fa4  test    rcx, rcx
0x180032fa7  jz      short loc_180032FAF
0x180032fa9  call    cs:__imp_CloseHandle
0x180032faf  mov     [rbx+310h], rdi
0x180032fb6  test    rdi, rdi
0x180032fb9  jnz     short loc_180032FE4
0x180032fbb  mov     rcx, [rsp+0A8h]; this
0x180032fc3  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180032fca  mov     edx, 115Dh; void *
0x180032fcf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180032fd4  mov     edi, eax
0x180032fd6  test    eax, eax
0x180032fd8  jns     short loc_180032FE4
0x180032fda  mov     edx, 11A1h
0x180032fdf  jmp     loc_180032EE2
0x180032fe4  mov     rcx, rbx; this
0x180032fe7  call    ?CreateDeploymentWorker@CUpdateDeploymentJob@@AEAAJXZ; CUpdateDeploymentJob::CreateDeploymentWorker(void)
0x180032fec  mov     edi, eax
0x180032fee  test    eax, eax
0x180032ff0  jns     short loc_180032FFC
0x180032ff2  mov     edx, 11A2h
0x180032ff7  jmp     loc_180032EE2
0x180032ffc  mov     rcx, rbx; this
0x180032fff  call    ?CreateCallbackWorker@CUpdateDeploymentJob@@AEAAJXZ; CUpdateDeploymentJob::CreateCallbackWorker(void)
0x180033004  mov     edi, eax
0x180033006  test    eax, eax
0x180033008  jns     short loc_180033014
0x18003300a  mov     edx, 11A3h
0x18003300f  jmp     loc_180032EE2
0x180033014  lea     rdi, [rbx+10h]
0x180033018  mov     rcx, rdi
0x18003301b  lea     rdx, [rbx+3D8h]
0x180033022  call    ?CreateUDPPrivateNamespace@mutex@@YAJAEAU_GUID@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?LocalClosePrivateNamespace@mutex@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; mutex::CreateUDPPrivateNamespace(_GUID &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x180033027  mov     ebx, eax
0x180033029  test    eax, eax
0x18003302b  jns     short loc_180033053
0x18003302d  mov     rcx, [rsp+0A8h]; this
0x180033035  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18003303c  mov     r9d, eax; char *
0x18003303f  mov     edx, 117Bh; void *
0x180033044  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033049  mov     edx, 11A4h
0x18003304e  jmp     loc_180032D7F
0x180033053  mov     rdx, rdi; struct _GUID *
0x180033056  lea     rcx, [rsp+0A8h+var_68]; this
0x18003305b  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180033060  mov     [rsp+0A8h+var_78], rax
0x180033065  xor     edx, edx
0x180033067  lea     rax, aDeploymentJobI_51; "Deployment job Id %ws : Initialized suc"...
0x18003306e  xor     ecx, ecx
0x180033070  mov     [rsp+0A8h+var_80], rax
0x180033075  mov     r8d, 1000000h
0x18003307b  mov     [rsp+0A8h+var_88], 0
0x180033084  lea     r9d, [rdx+4]
0x180033088  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003308d  xor     eax, eax
0x18003308f  lea     r11, [rsp+0A8h+var_18]
0x180033097  mov     rbx, [r11+20h]
0x18003309b  mov     rbp, [r11+28h]
0x18003309f  mov     rsi, [r11+30h]
0x1800330a3  mov     rdi, [r11+38h]
0x1800330a7  mov     rsp, r11
0x1800330aa  pop     r15
0x1800330ac  pop     r14
0x1800330ae  pop     r12
0x1800330b0  retn
```
