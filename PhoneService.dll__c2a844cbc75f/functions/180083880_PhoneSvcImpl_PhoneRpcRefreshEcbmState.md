# PhoneSvcImpl_PhoneRpcRefreshEcbmState

- ea: `0x180083880`
- end: `0x180083aeb`
- name: `PhoneSvcImpl_PhoneRpcRefreshEcbmState`
- size: `619`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006e94`
- `0x18004c2ac`
- `0x180080894`
- `0x180083880`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008395d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083983`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800839f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083a5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083acd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008395d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083983`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800839f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083a5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180083acd`
- `PhoneUtil!CreatePerUserSecurityTokenForRpcClient` at `0x18008390f`
- `PhoneUtil!CreatePerUserSecurityTokenForRpcClient` at `0x18008390f`

## string_xrefs

- `0x1800838c5`: `onecoreuap\net\phone\phoneservice\service\lib\internalphonerpc.cpp`
- `0x180083928`: `onecoreuap\net\phone\phoneservice\service\lib\internalphonerpc.cpp`
- `0x1800839c1`: `onecoreuap\net\phone\phoneservice\service\lib\internalphonerpc.cpp`
- `0x180083a9c`: `onecoreuap\net\phone\phoneservice\service\lib\internalphonerpc.cpp`

## pseudocode

```c
__int64 PhoneSvcImpl_PhoneRpcRefreshEcbmState()
{
  int v0; // eax
  BackTraceCollection *v1; // rcx
  unsigned int v2; // ebx
  int v4; // eax
  BackTraceCollection *v5; // rcx
  __int64 (__fastcall *v6)(_QWORD, __int64, HLOCAL *, unsigned int *, struct ISecurityToken *); // rsi
  int v7; // eax
  BackTraceCollection *v8; // rcx
  unsigned int v9; // edi
  unsigned int v10; // edi
  int v11; // eax
  BackTraceCollection *v12; // rcx
  unsigned int v13; // esi
  HLOCAL hMem; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v15; // [rsp+40h] [rbp-28h] BYREF
  struct ISecurityToken *v16; // [rsp+48h] [rbp-20h] BYREF

  v0 = WrappedComPtrBase<IPhoneController,DoesNotSupportShutdown,utl::recursive_mutex>::Get(&g_phoneRpcServer);
  v2 = v0;
  if ( v0 < 0 )
  {
    BackTraceCollection::Capture(v1, v0);
    Log_HREvent_28(v2, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\internalphonerpc.cpp", 869);
    return v2;
  }
  hMem = 0;
  v15 = 0;
  v16 = 0;
  v4 = CreatePerUserSecurityTokenForRpcClient(&v16);
  v2 = v4;
  if ( v4 < 0 )
  {
    BackTraceCollection::Capture(v5, v4);
    Log_HREvent_28(v2, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\internalphonerpc.cpp", 879);
    if ( v16 )
      (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v16 + 16LL))(v16);
    return v2;
  }
  v6 = *(__int64 (__fastcall **)(_QWORD, __int64, HLOCAL *, unsigned int *, struct ISecurityToken *))(MEMORY[0] + 432LL);
  hMem = 0;
  v7 = v6(0, 193, &hMem, &v15, v16);
  v9 = v7;
  if ( v7 >= 0 )
  {
    v10 = 0;
    if ( v15 )
    {
      while ( 1 )
      {
        v11 = (*(__int64 (__fastcall **)(_QWORD, char *))(MEMORY[0] + 192LL))(0, (char *)hMem + 16 * v10);
        v13 = v11;
        if ( v11 < 0 )
          break;
        if ( ++v10 >= v15 )
          goto LABEL_17;
      }
      BackTraceCollection::Capture(v12, v11);
      Log_HREvent_28(v13, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\internalphonerpc.cpp", 885);
      if ( v16 )
        (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v16 + 16LL))(v16);
      if ( hMem )
        LocalFree(hMem);
      return v13;
    }
    else
    {
LABEL_17:
      if ( v16 )
        (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v16 + 16LL))(v16);
      if ( hMem )
        LocalFree(hMem);
      return 0;
    }
  }
  else
  {
    BackTraceCollection::Capture(v8, v7);
    Log_HREvent_28(v9, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\internalphonerpc.cpp", 881);
    if ( v16 )
      (*(void (__fastcall **)(struct ISecurityToken *))(*(_QWORD *)v16 + 16LL))(v16);
    if ( hMem )
      LocalFree(hMem);
    return v9;
  }
}

```

## disassembly

```asm
0x180083880  push    rbp
0x180083882  push    rbx
0x180083883  push    rsi
0x180083884  push    rdi
0x180083885  mov     rbp, rsp
0x180083888  sub     rsp, 68h
0x18008388c  mov     rax, cs:__security_cookie
0x180083893  xor     rax, rsp
0x180083896  mov     [rbp+var_18], rax
0x18008389a  lea     rdx, [rbp+var_38]
0x18008389e  mov     [rbp+var_38], 0
0x1800838a6  lea     rcx, ?g_phoneRpcServer@@3VSecurePhoneRpcServer@@A; lpCriticalSection
0x1800838ad  call    ?Get@?$WrappedComPtrBase@UIPhoneController@@VDoesNotSupportShutdown@@Vrecursive_mutex@utl@@@@QEAAJPEAPEAUIPhoneController@@@Z; WrappedComPtrBase<IPhoneController,DoesNotSupportShutdown,utl::recursive_mutex>::Get(IPhoneController * *)
0x1800838b2  mov     ebx, eax
0x1800838b4  test    eax, eax
0x1800838b6  jns     short loc_1800838F4
0x1800838b8  mov     edx, eax; int
0x1800838ba  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800838bf  mov     r9d, 365h
0x1800838c5  lea     r8, aOnecoreuapNetP_16; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800838cc  mov     edx, 1
0x1800838d1  mov     ecx, ebx
0x1800838d3  call    Log_HREvent_28
0x1800838d8  mov     rcx, [rbp+var_38]
0x1800838dc  test    rcx, rcx
0x1800838df  jz      short loc_1800838ED
0x1800838e1  mov     rax, [rcx]
0x1800838e4  mov     rax, [rax+10h]
0x1800838e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800838ed  mov     eax, ebx
0x1800838ef  jmp     loc_180083A7A
0x1800838f4  lea     rcx, [rbp+var_20]
0x1800838f8  mov     [rbp+hMem], 0
0x180083900  mov     [rbp+var_28], 0
0x180083907  mov     [rbp+var_20], 0
0x18008390f  call    cs:__imp_?CreatePerUserSecurityTokenForRpcClient@@YAJPEAPEAUISecurityToken@@@Z; CreatePerUserSecurityTokenForRpcClient(ISecurityToken * *)
0x180083915  mov     ebx, eax
0x180083917  test    eax, eax
0x180083919  jns     short loc_180083968
0x18008391b  mov     edx, eax; int
0x18008391d  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180083922  mov     r9d, 36Fh
0x180083928  lea     r8, aOnecoreuapNetP_16; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18008392f  mov     edx, 1
0x180083934  mov     ecx, ebx
0x180083936  call    Log_HREvent_28
0x18008393b  mov     rcx, [rbp+var_20]
0x18008393f  test    rcx, rcx
0x180083942  jz      short loc_180083950
0x180083944  mov     rax, [rcx]
0x180083947  mov     rax, [rax+10h]
0x18008394b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083950  mov     rcx, [rbp+hMem]; hMem
0x180083954  test    rcx, rcx
0x180083957  jz      loc_1800838D8
0x18008395d  call    cs:__imp_LocalFree
0x180083963  jmp     loc_1800838D8
0x180083968  mov     rbx, [rbp+var_38]
0x18008396c  mov     rcx, [rbp+hMem]; hMem
0x180083970  mov     rdi, [rbp+var_20]
0x180083974  mov     rax, [rbx]
0x180083977  mov     rsi, [rax+1B0h]
0x18008397e  test    rcx, rcx
0x180083981  jz      short loc_180083989
0x180083983  call    cs:__imp_LocalFree
0x180083989  lea     r9, [rbp+var_28]
0x18008398d  mov     [rbp+hMem], 0
0x180083995  lea     r8, [rbp+hMem]
0x180083999  mov     [rsp+68h+var_48], rdi
0x18008399e  mov     edx, 0C1h
0x1800839a3  mov     rcx, rbx
0x1800839a6  mov     rax, rsi
0x1800839a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800839ae  mov     edi, eax
0x1800839b0  test    eax, eax
0x1800839b2  jns     short loc_180083A10
0x1800839b4  mov     edx, eax; int
0x1800839b6  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800839bb  mov     r9d, 371h
0x1800839c1  lea     r8, aOnecoreuapNetP_16; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800839c8  mov     edx, 1
0x1800839cd  mov     ecx, edi
0x1800839cf  call    Log_HREvent_28
0x1800839d4  mov     rcx, [rbp+var_20]
0x1800839d8  test    rcx, rcx
0x1800839db  jz      short loc_1800839E9
0x1800839dd  mov     rax, [rcx]
0x1800839e0  mov     rax, [rax+10h]
0x1800839e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800839e9  mov     rcx, [rbp+hMem]; hMem
0x1800839ed  test    rcx, rcx
0x1800839f0  jz      short loc_1800839F8
0x1800839f2  call    cs:__imp_LocalFree
0x1800839f8  test    rbx, rbx
0x1800839fb  jz      short loc_180083A0C
0x1800839fd  mov     rax, [rbx]
0x180083a00  mov     rcx, rbx
0x180083a03  mov     rax, [rax+10h]
0x180083a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a0c  mov     eax, edi
0x180083a0e  jmp     short loc_180083A7A
0x180083a10  xor     edi, edi
0x180083a12  cmp     [rbp+var_28], edi
0x180083a15  jbe     short loc_180083A40
0x180083a17  mov     rax, [rbx]
0x180083a1a  mov     rcx, rbx
0x180083a1d  mov     edx, edi
0x180083a1f  shl     rdx, 4
0x180083a23  add     rdx, [rbp+hMem]
0x180083a27  mov     rax, [rax+0C0h]
0x180083a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a33  mov     esi, eax
0x180083a35  test    eax, eax
0x180083a37  js      short loc_180083A8F
0x180083a39  inc     edi
0x180083a3b  cmp     edi, [rbp+var_28]
0x180083a3e  jb      short loc_180083A17
0x180083a40  mov     rcx, [rbp+var_20]
0x180083a44  test    rcx, rcx
0x180083a47  jz      short loc_180083A55
0x180083a49  mov     rax, [rcx]
0x180083a4c  mov     rax, [rax+10h]
0x180083a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a55  mov     rcx, [rbp+hMem]; hMem
0x180083a59  test    rcx, rcx
0x180083a5c  jz      short loc_180083A64
0x180083a5e  call    cs:__imp_LocalFree
0x180083a64  test    rbx, rbx
0x180083a67  jz      short loc_180083A78
0x180083a69  mov     rax, [rbx]
0x180083a6c  mov     rcx, rbx
0x180083a6f  mov     rax, [rax+10h]
0x180083a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083a78  xor     eax, eax
0x180083a7a  mov     rcx, [rbp+var_18]
0x180083a7e  xor     rcx, rsp; StackCookie
0x180083a81  call    __security_check_cookie
0x180083a86  add     rsp, 68h
0x180083a8a  pop     rdi
0x180083a8b  pop     rsi
0x180083a8c  pop     rbx
0x180083a8d  pop     rbp
0x180083a8e  retn
0x180083a8f  mov     edx, esi; int
0x180083a91  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180083a96  mov     r9d, 375h
0x180083a9c  lea     r8, aOnecoreuapNetP_16; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180083aa3  mov     edx, 1
0x180083aa8  mov     ecx, esi
0x180083aaa  call    Log_HREvent_28
0x180083aaf  mov     rcx, [rbp+var_20]
0x180083ab3  test    rcx, rcx
0x180083ab6  jz      short loc_180083AC4
0x180083ab8  mov     rax, [rcx]
0x180083abb  mov     rax, [rax+10h]
0x180083abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083ac4  mov     rcx, [rbp+hMem]; hMem
0x180083ac8  test    rcx, rcx
0x180083acb  jz      short loc_180083AD3
0x180083acd  call    cs:__imp_LocalFree
0x180083ad3  test    rbx, rbx
0x180083ad6  jz      short loc_180083AE7
0x180083ad8  mov     rax, [rbx]
0x180083adb  mov     rcx, rbx
0x180083ade  mov     rax, [rax+10h]
0x180083ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083ae7  mov     eax, esi
0x180083ae9  jmp     short loc_180083A7A
```
