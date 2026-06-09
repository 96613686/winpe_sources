# wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180024b40`
- end: `0x180024cb7`
- name: `?Stop@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180024694`

## callees

- `0x1800017ac`
- `0x180003bb0`
- `0x180004708`
- `0x18000a9b0`
- `0x180016c9c`
- `0x1800241f8`
- `0x180024274`
- `0x180024b40`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024ba5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180024ba5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024bfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024bfc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  __int64 v2; // rax
  int v3; // edi
  int v4; // edi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rax
  const struct wil::FailureInfo *v8; // rdx
  DWORD CurrentThreadId; // [rsp+30h] [rbp-79h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-71h] BYREF
  __int64 v11; // [rsp+40h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12[2]; // [rsp+50h] [rbp-59h] BYREF
  __int64 *v13; // [rsp+70h] [rbp-39h]
  __int64 v14; // [rsp+78h] [rbp-31h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-29h]
  __int64 v16; // [rsp+88h] [rbp-21h]
  DWORD *p_CurrentThreadId; // [rsp+90h] [rbp-19h]
  __int64 v18; // [rsp+98h] [rbp-11h]

  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v2 = a1[34];
  v3 = *(_DWORD *)(v2 + 248);
  if ( v3 < 1 )
  {
    memset_0(v12, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v12, v8);
  }
  if ( *(int *)(v2 + 72) >= 0 )
    *(_DWORD *)(v2 + 72) = 0;
  v4 = v3 - 1;
  *(_DWORD *)(v2 + 248) = v4;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  if ( v4 )
  {
    v5 = WaasMedic::TelemetryProvider::Provider();
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (v7 & 0x400000000000LL) == v7 )
      {
        CurrentThreadId = GetCurrentThreadId();
        LODWORD(SRWLock) = 0;
        v11 = 0x1000000;
        p_CurrentThreadId = &CurrentThreadId;
        v18 = 4;
        p_SRWLock = &SRWLock;
        v16 = 4;
        v13 = &v11;
        v14 = 8;
        tlgWriteTransfer_EventWriteTransfer(
          v6,
          (unsigned __int8 *)byte_180088C17,
          (const GUID *)(a1[34] + 8LL),
          0,
          5u,
          v12);
      }
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x180024b40  mov     [rsp-8+arg_8], rbx
0x180024b45  mov     [rsp-8+arg_10], rdi
0x180024b4a  push    rbp
0x180024b4b  lea     rbp, [rsp-57h]
0x180024b50  sub     rsp, 100h
0x180024b57  mov     rax, cs:__security_cookie
0x180024b5e  xor     rax, rsp
0x180024b61  mov     [rbp+57h+var_10], rax
0x180024b65  mov     rbx, rcx
0x180024b68  lea     rdx, [rbp+57h+SRWLock]
0x180024b6c  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180024b71  mov     rax, [rbx+110h]
0x180024b78  mov     edi, [rax+0F8h]
0x180024b7e  cmp     edi, 1
0x180024b81  jl      loc_180024C9C
0x180024b87  cmp     dword ptr [rax+48h], 0
0x180024b8b  jl      short loc_180024B94
0x180024b8d  mov     dword ptr [rax+48h], 0
0x180024b94  dec     edi
0x180024b96  mov     [rax+0F8h], edi
0x180024b9c  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180024ba0  test    rcx, rcx
0x180024ba3  jz      short loc_180024BAB
0x180024ba5  call    cs:__imp_ReleaseSRWLockExclusive
0x180024bab  test    edi, edi
0x180024bad  jnz     short loc_180024BC3
0x180024baf  mov     rax, [rbx]
0x180024bb2  mov     rcx, rbx
0x180024bb5  mov     rax, [rax+8]
0x180024bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bbe  jmp     loc_180024C72
0x180024bc3  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180024bc8  mov     rdi, rax
0x180024bcb  mov     ecx, [rax]
0x180024bcd  cmp     ecx, 5
0x180024bd0  jbe     loc_180024C72
0x180024bd6  mov     rax, [rax+18h]
0x180024bda  mov     rcx, [rdi+10h]
0x180024bde  mov     rdx, 400000000000h
0x180024be8  test    rdx, rcx
0x180024beb  jz      loc_180024C72
0x180024bf1  mov     rcx, rax
0x180024bf4  and     rcx, rdx
0x180024bf7  cmp     rcx, rax
0x180024bfa  jnz     short loc_180024C72
0x180024bfc  call    cs:__imp_GetCurrentThreadId
0x180024c02  mov     [rbp+57h+var_D0], eax
0x180024c05  mov     dword ptr [rbp+57h+SRWLock], 0
0x180024c0c  mov     [rbp+57h+var_C0], 1000000h
0x180024c14  lea     rax, [rbp+57h+var_D0]
0x180024c18  mov     [rbp+57h+var_70], rax
0x180024c1c  mov     [rbp+57h+var_68], 4
0x180024c24  lea     rax, [rbp+57h+SRWLock]
0x180024c28  mov     [rbp+57h+var_80], rax
0x180024c2c  mov     [rbp+57h+var_78], 4
0x180024c34  lea     rax, [rbp+57h+var_C0]
0x180024c38  mov     [rbp+57h+var_90], rax
0x180024c3c  mov     [rbp+57h+var_88], 8
0x180024c44  mov     r8, [rbx+110h]
0x180024c4b  add     r8, 8
0x180024c4f  lea     rax, [rbp+57h+var_B0]
0x180024c53  mov     [rsp+100h+var_D8], rax
0x180024c58  mov     [rsp+100h+var_E0], 5
0x180024c60  xor     r9d, r9d
0x180024c63  lea     rdx, byte_180088C17
0x180024c6a  mov     rcx, rdi
0x180024c6d  call    _tlgWriteTransfer_EventWriteTransfer
0x180024c72  mov     rcx, rbx
0x180024c75  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180024c7a  nop
0x180024c7b  mov     rcx, [rbp+57h+var_10]
0x180024c7f  xor     rcx, rsp; StackCookie
0x180024c82  call    __security_check_cookie
0x180024c87  lea     r11, [rsp+100h+var_s0]
0x180024c8f  mov     rbx, [r11+18h]
0x180024c93  mov     rdi, [r11+20h]
0x180024c97  mov     rsp, r11
0x180024c9a  pop     rbp
0x180024c9b  retn
0x180024c9c  xor     edx, edx; Val
0x180024c9e  mov     r8d, 98h; Size
0x180024ca4  lea     rcx, [rbp+57h+var_B0]; void *
0x180024ca8  call    memset_0
0x180024cad  lea     rcx, [rbp+57h+var_B0]; this
0x180024cb1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
