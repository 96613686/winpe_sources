# winrt::Windows::Management::Update::implementation::WindowsUpdateRestartRequestOptions::~WindowsUpdateRestartRequestOptions(void)

- ea: `0x180012628`
- end: `0x180012723`
- name: `??1WindowsUpdateRestartRequestOptions@implementation@Update@Management@Windows@winrt@@UEAA@XZ`
- size: `251`
- prototype: `void __fastcall(winrt::Windows::Management::Update::implementation::WindowsUpdateRestartRequestOptions *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012c40`

## callees

- `0x180008bf4`
- `0x180008c0c`
- `0x18001234c`
- `0x180012628`
- `0x180017c3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800126f4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012705`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012716`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800126f4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012705`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180012716`

## pseudocode

```c
void __fastcall winrt::Windows::Management::Update::implementation::WindowsUpdateRestartRequestOptions::~WindowsUpdateRestartRequestOptions(
        winrt::Windows::Management::Update::implementation::WindowsUpdateRestartRequestOptions *this)
{
  volatile signed __int32 *v1; // rdi
  int v3; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v5; // rdi
  int v6; // eax
  HANDLE v7; // rax
  volatile signed __int32 *v8; // rdi
  int v9; // esi
  HANDLE v10; // rax

  v1 = (volatile signed __int32 *)*((_QWORD *)this + 7);
  if ( v1 )
  {
    v3 = _InterlockedDecrement(v1 + 6);
    if ( v3 )
    {
      if ( v3 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v1);
    }
    *((_QWORD *)this + 7) = 0;
  }
  if ( *((_QWORD *)this + 5) )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((__int64 *)this + 5);
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  if ( v5 )
  {
    v6 = _InterlockedDecrement(v5 + 6);
    if ( v6 )
    {
      if ( v6 < 0 )
        abort();
    }
    else
    {
      v7 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v7, 0, (LPVOID)v5);
    }
    *((_QWORD *)this + 4) = 0;
  }
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  if ( v8 )
  {
    v9 = _InterlockedDecrement(v8 + 6);
    if ( v9 )
    {
      if ( v9 < 0 )
        abort();
    }
    else
    {
      v10 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v10, 0, (LPVOID)v8);
    }
    *((_QWORD *)this + 3) = 0;
  }
  winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>((__int64)this);
}

```

## disassembly

```asm
0x180012628  mov     [rsp+arg_0], rbx
0x18001262d  mov     [rsp+arg_8], rsi
0x180012632  push    rdi
0x180012633  sub     rsp, 20h
0x180012637  mov     rdi, [rcx+38h]
0x18001263b  or      esi, 0FFFFFFFFh
0x18001263e  mov     rbx, rcx
0x180012641  test    rdi, rdi
0x180012644  jz      short loc_18001266E
0x180012646  mov     eax, esi
0x180012648  lock xadd [rdi+18h], eax
0x18001264d  sub     eax, 1
0x180012650  jnz     loc_1800126EC
0x180012656  nop
0x180012657  call    WINRT_IMPL_GetProcessHeap
0x18001265c  mov     rcx, rax; hHeap
0x18001265f  mov     r8, rdi; lpMem
0x180012662  xor     edx, edx; dwFlags
0x180012664  call    WINRT_IMPL_HeapFree
0x180012669  and     qword ptr [rbx+38h], 0
0x18001266e  lea     rcx, [rbx+28h]
0x180012672  cmp     qword ptr [rcx], 0
0x180012676  jz      short loc_18001267D
0x180012678  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001267d  mov     rdi, [rbx+20h]
0x180012681  test    rdi, rdi
0x180012684  jz      short loc_1800126AA
0x180012686  mov     eax, esi
0x180012688  lock xadd [rdi+18h], eax
0x18001268d  sub     eax, 1
0x180012690  jnz     short loc_180012701
0x180012692  nop
0x180012693  call    WINRT_IMPL_GetProcessHeap
0x180012698  mov     rcx, rax; hHeap
0x18001269b  mov     r8, rdi; lpMem
0x18001269e  xor     edx, edx; dwFlags
0x1800126a0  call    WINRT_IMPL_HeapFree
0x1800126a5  and     qword ptr [rbx+20h], 0
0x1800126aa  mov     rdi, [rbx+18h]
0x1800126ae  test    rdi, rdi
0x1800126b1  jz      short loc_1800126D5
0x1800126b3  lock xadd [rdi+18h], esi
0x1800126b8  sub     esi, 1
0x1800126bb  jnz     short loc_180012712
0x1800126bd  nop
0x1800126be  call    WINRT_IMPL_GetProcessHeap
0x1800126c3  mov     rcx, rax; hHeap
0x1800126c6  mov     r8, rdi; lpMem
0x1800126c9  xor     edx, edx; dwFlags
0x1800126cb  call    WINRT_IMPL_HeapFree
0x1800126d0  and     qword ptr [rbx+18h], 0
0x1800126d5  mov     rcx, rbx
0x1800126d8  mov     rbx, [rsp+28h+arg_0]
0x1800126dd  mov     rsi, [rsp+28h+arg_8]
0x1800126e2  add     rsp, 20h
0x1800126e6  pop     rdi
0x1800126e7  jmp     ??1?$root_implements@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>(void)
0x1800126ec  test    eax, eax
0x1800126ee  jns     loc_180012669
0x1800126f4  call    cs:__imp_abort
0x180012701  test    eax, eax
0x180012703  jns     short loc_1800126A5
0x180012705  call    cs:__imp_abort
0x180012712  test    esi, esi
0x180012714  jns     short loc_1800126D0
0x180012716  call    cs:__imp_abort
```
