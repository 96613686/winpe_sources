# SipcEndpoint::CreateClientEndpoint(SipcClient *,unsigned __int64,void (*)(ISIPCEndpoint *,SIPC_BUFFER_STATUS,SIPC_BUFFER_INFO const *,SIPC_BUFFER_INFO const *,void *),void (*)(ISIPCEndpoint *,SIPC_ENDPOINT_STATUS,void *),void *,uint *,SipcEndpoint * *)

- ea: `0x180026d6c`
- end: `0x180027039`
- name: `?CreateClientEndpoint@SipcEndpoint@@SAJPEAVSipcClient@@_KP6AXPEAUISIPCEndpoint@@W4SIPC_BUFFER_STATUS@@PEBUSIPC_BUFFER_INFO@@4PEAX@ZP6AX2W4SIPC_ENDPOINT_STATUS@@5@Z5PEAIPEAPEAV1@@Z`
- size: `717`
- prototype: `static int(struct SipcClient *, unsigned __int64, void (__high *)(struct ISIPCEndpoint *, enum SIPC_BUFFER_STATUS, const struct SIPC_BUFFER_INFO *, const struct SIPC_BUFFER_INFO *, void *), void (__high *)(struct ISIPCEndpoint *, enum SIPC_ENDPOINT_STATUS, void *), void *, unsigned int *, struct SipcEndpoint **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180026260`

## callees

- `0x180024c48`
- `0x180025178`
- `0x180026a4c`
- `0x180026d6c`
- `0x180027040`
- `0x180027214`
- `0x18002774c`
- `0x18002a1e8`
- `0x18002ad20`
- `0x18004c8a5`
- `0x18004c8e0`
- `0x18004d010`

## import_xrefs

- `ntdll!NtQueryLicenseValue` at `0x180026e97`
- `ntdll!NtQueryLicenseValue` at `0x180026e97`
- `ntdll!RtlInitUnicodeString` at `0x180026e71`
- `ntdll!RtlInitUnicodeString` at `0x180026e71`
- `ntdll!RtlAllocateHeap` at `0x180026de1`
- `ntdll!RtlAllocateHeap` at `0x180026de1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026fe1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180026fe1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026e07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026e07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026df9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026df9`

## pseudocode

```c
__int64 __fastcall SipcEndpoint::CreateClientEndpoint(
        struct SipcClient *a1,
        unsigned __int64 a2,
        void (__high *a3)(struct ISIPCEndpoint *, enum SIPC_BUFFER_STATUS, const struct SIPC_BUFFER_INFO *, const struct SIPC_BUFFER_INFO *, void *),
        void (__high *a4)(struct ISIPCEndpoint *, enum SIPC_ENDPOINT_STATUS, void *),
        void *a5,
        unsigned int *a6,
        struct SipcEndpoint **a7)
{
  PVOID Heap; // rdi
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  __int64 v14; // rbx
  _QWORD *v15; // r15
  unsigned int *v16; // r14
  int ClientEvents; // edi
  unsigned __int16 v18; // ax
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  unsigned int v22; // eax
  unsigned int *v23; // rcx
  int v25; // [rsp+30h] [rbp-D0h]
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int *v28; // [rsp+58h] [rbp-A8h]
  struct SipcEndpoint **v29; // [rsp+60h] [rbp-A0h]
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+80h] [rbp-80h] BYREF
  char v32[76]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v33; // [rsp+D4h] [rbp-2Ch] BYREF
  char v34[68]; // [rsp+E4h] [rbp-1Ch] BYREF
  char v35[72]; // [rsp+128h] [rbp+28h] BYREF

  v29 = a7;
  *a6 = 0;
  *a7 = 0;
  v28 = a6;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x60u);
  if ( !Heap )
    return 2147942414LL;
  CurrentThreadId = GetCurrentThreadId();
  CurrentProcessId = GetCurrentProcessId();
  v14 = SipcEndpoint::SipcEndpoint(
          Heap,
          -(__int64)(a1 != 0) & ((unsigned __int64)a1 + 16),
          0,
          CurrentProcessId,
          CurrentThreadId,
          a3,
          a4,
          a5);
  if ( !v14 )
    return 2147942414LL;
  v26 = 0;
  v27 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"Kernel-ProductInfo");
  if ( (int)NtQueryLicenseValue(&DestinationString, 0, &v26, 4, &v27) < 0 || (unsigned int)(v26 - 194) > 1 )
  {
    v31 = 0;
    memset_0(v32, 0, sizeof(v32));
    v33 = 0;
    memset_0(v34, 0, sizeof(v34));
    memset_0(v35, 0, 0x44u);
    ClientEvents = SipcPrivateNamespace::Create((SipcPrivateNamespace *)&v31);
    if ( ClientEvents >= 0 )
    {
      ClientEvents = SipcSignalFactory::CreateClientEvents(
                       (const struct SipcPrivateNamespace *)&v31,
                       (void **)(v14 + 24),
                       (void **)(v14 + 32));
      if ( ClientEvents >= 0 )
      {
        LOBYTE(v20) = *((_BYTE *)a1 + 45);
        LOBYTE(v19) = *((_BYTE *)a1 + 44);
        LOWORD(v25) = 0;
        ClientEvents = AlpcPort::CreateClientPort(
                         (char *)a1 + 24,
                         *((unsigned int *)a1 + 10),
                         v19,
                         v20,
                         &v33,
                         a2,
                         v25,
                         *((_QWORD *)a1 + 6),
                         v14 + 64,
                         v14 + 16);
      }
    }
    SipcPrivateNamespace::~SipcPrivateNamespace((SipcPrivateNamespace *)&v31);
    v16 = (unsigned int *)(v14 + 64);
    v15 = (_QWORD *)(v14 + 16);
  }
  else
  {
    v15 = (_QWORD *)(v14 + 16);
    v16 = (unsigned int *)(v14 + 64);
    ClientEvents = XvmmPort::CreateClientPort(
                     (const struct _GUID *)((char *)a1 + 24),
                     *((_BYTE *)a1 + 44),
                     *((_BYTE *)a1 + 45),
                     a2,
                     (unsigned int *)(v14 + 64),
                     (struct SipcPort **)(v14 + 16));
    if ( ClientEvents < 0 )
    {
LABEL_17:
      SipcObjectBase<ISIPCEndpoint>::Release(v14);
      return (unsigned int)ClientEvents;
    }
    v18 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 48LL))(*v15);
    ClientEvents = SipcSignalFactory::OpenClientEvents(v18, (void **)(v14 + 24), (void **)(v14 + 32));
  }
  if ( ClientEvents < 0 )
    goto LABEL_17;
  if ( *v16 )
  {
    v21 = *v15;
    if ( *(_BYTE *)(*v15 + 44LL) )
    {
      *(_BYTE *)(v21 + 44) = 0;
      if ( *(_DWORD *)(v21 + 40) )
        ResetEvent(*(HANDLE *)(v21 + 32));
    }
  }
  v22 = *v16;
  v23 = v28;
  *(_BYTE *)(v14 + 60) = 1;
  *v23 = v22;
  *v29 = (struct SipcEndpoint *)v14;
  return 0;
}

```

## disassembly

```asm
0x180026d6c  push    rbp
0x180026d6e  push    rbx
0x180026d6f  push    rsi
0x180026d70  push    rdi
0x180026d71  push    r12
0x180026d73  push    r13
0x180026d75  push    r14
0x180026d77  push    r15
0x180026d79  lea     rbp, [rsp-88h]
0x180026d81  sub     rsp, 188h
0x180026d88  mov     rax, cs:__security_cookie
0x180026d8f  xor     rax, rsp
0x180026d92  mov     [rbp+0C0h+var_50], rax
0x180026d96  mov     rax, [rbp+0C0h+arg_28]
0x180026d9d  mov     rsi, rcx
0x180026da0  mov     rcx, [rbp+0C0h+arg_30]
0x180026da7  mov     r12, rdx
0x180026daa  mov     r13, [rbp+0C0h+arg_20]
0x180026db1  xor     edx, edx; Flags
0x180026db3  mov     [rsp+1C0h+var_160], rcx
0x180026db8  mov     r14, r8
0x180026dbb  mov     dword ptr [rax], 0
0x180026dc1  mov     r15, r9
0x180026dc4  mov     qword ptr [rcx], 0
0x180026dcb  mov     rcx, gs:60h
0x180026dd4  lea     r8d, [rdx+60h]; Size
0x180026dd8  mov     [rsp+1C0h+var_168], rax
0x180026ddd  mov     rcx, [rcx+30h]; HeapHandle
0x180026de1  call    cs:__imp_RtlAllocateHeap
0x180026de8  nop     dword ptr [rax+rax+00h]
0x180026ded  mov     rdi, rax
0x180026df0  test    rax, rax
0x180026df3  jz      loc_180027013
0x180026df9  call    cs:__imp_GetCurrentThreadId
0x180026e00  nop     dword ptr [rax+rax+00h]
0x180026e05  mov     ebx, eax
0x180026e07  call    cs:__imp_GetCurrentProcessId
0x180026e0e  nop     dword ptr [rax+rax+00h]
0x180026e13  mov     [rsp+1C0h+var_188], r13
0x180026e18  lea     rdx, [rsi+10h]
0x180026e1c  mov     [rsp+1C0h+var_190], r15
0x180026e21  mov     rcx, rsi
0x180026e24  neg     rcx
0x180026e27  mov     [rsp+1C0h+var_198], r14
0x180026e2c  mov     r9d, eax
0x180026e2f  mov     dword ptr [rsp+1C0h+var_1A0], ebx
0x180026e33  sbb     r10, r10
0x180026e36  mov     rcx, rdi
0x180026e39  and     rdx, r10
0x180026e3c  xor     r8d, r8d
0x180026e3f  call    ??0SipcEndpoint@@AEAA@PEAVSipcEndpointOwner@@W4SipcEndpointKind@@KKP6AXPEAUISIPCEndpoint@@W4SIPC_BUFFER_STATUS@@PEBUSIPC_BUFFER_INFO@@4PEAX@ZP6AX2W4SIPC_ENDPOINT_STATUS@@5@Z5@Z; SipcEndpoint::SipcEndpoint(SipcEndpointOwner *,SipcEndpointKind,ulong,ulong,void (*)(ISIPCEndpoint *,SIPC_BUFFER_STATUS,SIPC_BUFFER_INFO const *,SIPC_BUFFER_INFO const *,void *),void (*)(ISIPCEndpoint *,SIPC_ENDPOINT_STATUS,void *),void *)
0x180026e44  xor     r13d, r13d
0x180026e47  mov     rbx, rax
0x180026e4a  test    rax, rax
0x180026e4d  jz      loc_180027013
0x180026e53  xorps   xmm0, xmm0
0x180026e56  mov     [rsp+1C0h+var_170], r13d
0x180026e5b  lea     rdx, SourceString; "Kernel-ProductInfo"
0x180026e62  mov     [rsp+1C0h+var_16C], r13d
0x180026e67  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x180026e6c  movups  xmmword ptr [rsp+1C0h+DestinationString.Length], xmm0
0x180026e71  call    cs:__imp_RtlInitUnicodeString
0x180026e78  nop     dword ptr [rax+rax+00h]
0x180026e7d  lea     rax, [rsp+1C0h+var_16C]
0x180026e82  xor     edx, edx
0x180026e84  lea     r9d, [r13+4]
0x180026e88  mov     [rsp+1C0h+var_1A0], rax
0x180026e8d  lea     r8, [rsp+1C0h+var_170]
0x180026e92  lea     rcx, [rsp+1C0h+DestinationString]
0x180026e97  call    cs:__imp_NtQueryLicenseValue
0x180026e9e  nop     dword ptr [rax+rax+00h]
0x180026ea3  test    eax, eax
0x180026ea5  js      short loc_180026F0A
0x180026ea7  mov     eax, [rsp+1C0h+var_170]
0x180026eab  add     eax, 0FFFFFF3Eh
0x180026eb0  cmp     eax, 1
0x180026eb3  ja      short loc_180026F0A
0x180026eb5  mov     r8b, [rsi+2Dh]; unsigned __int8
0x180026eb9  lea     r15, [rbx+10h]
0x180026ebd  mov     dl, [rsi+2Ch]; unsigned __int8
0x180026ec0  lea     r14, [rbx+40h]
0x180026ec4  mov     [rsp+1C0h+var_198], r15; struct SipcPort **
0x180026ec9  lea     rcx, [rsi+18h]; struct _GUID *
0x180026ecd  mov     r9, r12; unsigned __int64
0x180026ed0  mov     [rsp+1C0h+var_1A0], r14; unsigned int *
0x180026ed5  call    ?CreateClientPort@XvmmPort@@SAJAEBU_GUID@@EE_KPEAIPEAPEAVSipcPort@@@Z; XvmmPort::CreateClientPort(_GUID const &,uchar,uchar,unsigned __int64,uint *,SipcPort * *)
0x180026eda  mov     edi, eax
0x180026edc  test    eax, eax
0x180026ede  js      loc_180027007
0x180026ee4  mov     rcx, [r15]
0x180026ee7  mov     rax, [rcx]
0x180026eea  mov     rax, [rax+30h]
0x180026eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ef3  lea     r8, [rbx+20h]; void **
0x180026ef7  movzx   ecx, ax; unsigned __int16
0x180026efa  lea     rdx, [rbx+18h]; void **
0x180026efe  call    ?OpenClientEvents@SipcSignalFactory@@SAJGPEAPEAX0@Z; SipcSignalFactory::OpenClientEvents(ushort,void * *,void * *)
0x180026f03  mov     edi, eax
0x180026f05  jmp     loc_180026FC1
0x180026f0a  xor     edx, edx; Val
0x180026f0c  mov     [rbp+0C0h+var_140], r13
0x180026f10  lea     rcx, [rbp+0C0h+var_138]; void *
0x180026f14  lea     r8d, [rdx+4Ch]; Size
0x180026f18  call    memset_0
0x180026f1d  xorps   xmm0, xmm0
0x180026f20  lea     rcx, [rbp+0C0h+var_DC]; void *
0x180026f24  mov     edi, 44h ; 'D'
0x180026f29  xor     edx, edx; Val
0x180026f2b  mov     r8d, edi; Size
0x180026f2e  movups  [rbp+0C0h+var_EC], xmm0
0x180026f32  call    memset_0
0x180026f37  mov     r8d, edi; Size
0x180026f3a  lea     rcx, [rbp+0C0h+var_98]; void *
0x180026f3e  xor     edx, edx; Val
0x180026f40  call    memset_0
0x180026f45  lea     rcx, [rbp+0C0h+var_140]; this
0x180026f49  call    ?Create@SipcPrivateNamespace@@QEAAJXZ; SipcPrivateNamespace::Create(void)
0x180026f4e  mov     edi, eax
0x180026f50  test    eax, eax
0x180026f52  js      short loc_180026FB0
0x180026f54  lea     r8, [rbx+20h]; void **
0x180026f58  lea     rdx, [rbx+18h]; void **
0x180026f5c  lea     rcx, [rbp+0C0h+var_140]; struct SipcPrivateNamespace *
0x180026f60  call    ?CreateClientEvents@SipcSignalFactory@@SAJAEBVSipcPrivateNamespace@@PEAPEAX1@Z; SipcSignalFactory::CreateClientEvents(SipcPrivateNamespace const &,void * *,void * *)
0x180026f65  mov     edi, eax
0x180026f67  test    eax, eax
0x180026f69  js      short loc_180026FB0
0x180026f6b  mov     r9b, [rsi+2Dh]
0x180026f6f  lea     rdx, [rbx+40h]
0x180026f73  mov     r8b, [rsi+2Ch]
0x180026f77  lea     rax, [rbx+10h]
0x180026f7b  mov     [rsp+1C0h+var_178], rax
0x180026f80  lea     rcx, [rsi+18h]
0x180026f84  mov     rax, [rsi+30h]
0x180026f88  mov     [rsp+1C0h+var_180], rdx
0x180026f8d  mov     edx, [rsi+28h]
0x180026f90  mov     [rsp+1C0h+var_188], rax
0x180026f95  lea     rax, [rbp+0C0h+var_EC]
0x180026f99  mov     word ptr [rsp+1C0h+var_190], r13w
0x180026f9f  mov     [rsp+1C0h+var_198], r12
0x180026fa4  mov     [rsp+1C0h+var_1A0], rax
0x180026fa9  call    ?CreateClientPort@AlpcPort@@SAJAEBU_GUID@@W4SIPC_SERVICE_BOUNDARY@@EEAEBUSipcPrivateNamespaceAttributes@@_KGPEAXPEAIPEAPEAVSipcPort@@@Z; AlpcPort::CreateClientPort(_GUID const &,SIPC_SERVICE_BOUNDARY,uchar,uchar,SipcPrivateNamespaceAttributes const &,unsigned __int64,ushort,void *,uint *,SipcPort * *)
0x180026fae  mov     edi, eax
0x180026fb0  lea     rcx, [rbp+0C0h+var_140]; this
0x180026fb4  call    ??1SipcPrivateNamespace@@QEAA@XZ; SipcPrivateNamespace::~SipcPrivateNamespace(void)
0x180026fb9  lea     r14, [rbx+40h]
0x180026fbd  lea     r15, [rbx+10h]
0x180026fc1  test    edi, edi
0x180026fc3  js      short loc_180027007
0x180026fc5  cmp     [r14], r13d
0x180026fc8  jz      short loc_180026FED
0x180026fca  mov     rcx, [r15]
0x180026fcd  cmp     [rcx+2Ch], r13b
0x180026fd1  jz      short loc_180026FED
0x180026fd3  mov     [rcx+2Ch], r13b
0x180026fd7  cmp     [rcx+28h], r13d
0x180026fdb  jz      short loc_180026FED
0x180026fdd  mov     rcx, [rcx+20h]; hEvent
0x180026fe1  call    cs:__imp_ResetEvent
0x180026fe8  nop     dword ptr [rax+rax+00h]
0x180026fed  mov     eax, [r14]
0x180026ff0  mov     rcx, [rsp+1C0h+var_168]
0x180026ff5  mov     byte ptr [rbx+3Ch], 1
0x180026ff9  mov     [rcx], eax
0x180026ffb  mov     rax, [rsp+1C0h+var_160]
0x180027000  mov     [rax], rbx
0x180027003  xor     eax, eax
0x180027005  jmp     short loc_180027018
0x180027007  mov     rcx, rbx
0x18002700a  call    ?Release@?$SipcObjectBase@UISIPCEndpoint@@@@UEAAKXZ; SipcObjectBase<ISIPCEndpoint>::Release(void)
0x18002700f  mov     eax, edi
0x180027011  jmp     short loc_180027018
0x180027013  mov     eax, 8007000Eh
0x180027018  mov     rcx, [rbp+0C0h+var_50]
0x18002701c  xor     rcx, rsp; StackCookie
0x18002701f  call    __security_check_cookie
0x180027024  add     rsp, 188h
0x18002702b  pop     r15
0x18002702d  pop     r14
0x18002702f  pop     r13
0x180027031  pop     r12
0x180027033  pop     rdi
0x180027034  pop     rsi
0x180027035  pop     rbx
0x180027036  pop     rbp
0x180027037  retn
```
