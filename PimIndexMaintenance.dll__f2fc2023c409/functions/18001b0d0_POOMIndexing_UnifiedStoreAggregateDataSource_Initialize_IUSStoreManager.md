# POOMIndexing::UnifiedStoreAggregateDataSource::Initialize(IUSStoreManager *)

- ea: `0x18001b0d0`
- end: `0x18001b196`
- name: `?Initialize@UnifiedStoreAggregateDataSource@POOMIndexing@@MEAAJPEAUIUSStoreManager@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(POOMIndexing::UnifiedStoreAggregateDataSource *__hidden this, struct IUSStoreManager *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001b0d0`
- `0x18001b288`
- `0x18001b400`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b12a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b12a`

## pseudocode

```c
__int64 __fastcall POOMIndexing::UnifiedStoreAggregateDataSource::Initialize(
        POOMIndexing::UnifiedStoreAggregateDataSource *this,
        struct IUSStoreManager *a2)
{
  __int64 v4; // rcx
  HRESULT Instance; // edi
  __int64 v6; // r8
  __int64 v7; // r9
  int Generation; // eax
  __int64 v10; // r8

  v4 = *((_QWORD *)this + 4);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *((_QWORD *)this + 4) = a2;
  (*(void (__fastcall **)(struct IUSStoreManager *))(*(_QWORD *)a2 + 8LL))(a2);
  Instance = CoCreateInstance(&CLSID_Application, 0, 1u, &GUID_a65ccaeb_6558_4656_ad3d_eccc00d00f0d, (LPVOID *)this + 5);
  if ( Instance < 0 )
  {
    v7 = 83;
LABEL_5:
    Log_HREvent_6((unsigned int)Instance, 1, v6, v7);
    return (unsigned int)Instance;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 56LL))(*((_QWORD *)this + 5), 0);
  if ( Instance < 0 )
  {
    v7 = 86;
    goto LABEL_5;
  }
  Generation = POOMIndexing::UnifiedStoreAggregateDataSource::LoadGeneration(this);
  if ( Generation < 0 )
    Log_HREvent_6((unsigned int)Generation, 0, v10, 88);
  return 0;
}

```

## disassembly

```asm
0x18001b0d0  mov     [rsp+arg_0], rbx
0x18001b0d5  mov     [rsp+arg_8], rsi
0x18001b0da  push    rdi
0x18001b0db  sub     rsp, 30h
0x18001b0df  mov     rbx, rcx
0x18001b0e2  mov     rdi, rdx
0x18001b0e5  mov     rcx, [rcx+20h]
0x18001b0e9  test    rcx, rcx
0x18001b0ec  jz      short loc_18001B0FA
0x18001b0ee  mov     rax, [rcx]
0x18001b0f1  mov     rax, [rax+10h]
0x18001b0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0fa  mov     [rbx+20h], rdi
0x18001b0fe  mov     rcx, rdi
0x18001b101  mov     rax, [rdi]
0x18001b104  mov     rax, [rax+8]
0x18001b108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b10d  xor     edx, edx; pUnkOuter
0x18001b10f  lea     rsi, [rbx+28h]
0x18001b113  lea     r9, _GUID_a65ccaeb_6558_4656_ad3d_eccc00d00f0d; riid
0x18001b11a  mov     [rsp+38h+ppv], rsi; ppv
0x18001b11f  lea     rcx, CLSID_Application; rclsid
0x18001b126  lea     r8d, [rdx+1]; dwClsContext
0x18001b12a  call    cs:__imp_CoCreateInstance
0x18001b130  mov     edi, eax
0x18001b132  test    eax, eax
0x18001b134  jns     short loc_18001B14C
0x18001b136  mov     r9d, 53h ; 'S'
0x18001b13c  mov     edx, 1
0x18001b141  mov     ecx, edi
0x18001b143  call    Log_HREvent_6
0x18001b148  mov     eax, edi
0x18001b14a  jmp     short loc_18001B186
0x18001b14c  mov     rcx, [rsi]
0x18001b14f  xor     edx, edx
0x18001b151  mov     rax, [rcx]
0x18001b154  mov     rax, [rax+38h]
0x18001b158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b15d  mov     edi, eax
0x18001b15f  test    eax, eax
0x18001b161  jns     short loc_18001B16B
0x18001b163  mov     r9d, 56h ; 'V'
0x18001b169  jmp     short loc_18001B13C
0x18001b16b  mov     rcx, rbx; this
0x18001b16e  call    ?LoadGeneration@UnifiedStoreAggregateDataSource@POOMIndexing@@AEAAJXZ; POOMIndexing::UnifiedStoreAggregateDataSource::LoadGeneration(void)
0x18001b173  test    eax, eax
0x18001b175  jns     short loc_18001B184
0x18001b177  xor     edx, edx
0x18001b179  mov     ecx, eax
0x18001b17b  lea     r9d, [rdx+58h]
0x18001b17f  call    Log_HREvent_6
0x18001b184  xor     eax, eax
0x18001b186  mov     rbx, [rsp+38h+arg_0]
0x18001b18b  mov     rsi, [rsp+38h+arg_8]
0x18001b190  add     rsp, 30h
0x18001b194  pop     rdi
0x18001b195  retn
```
