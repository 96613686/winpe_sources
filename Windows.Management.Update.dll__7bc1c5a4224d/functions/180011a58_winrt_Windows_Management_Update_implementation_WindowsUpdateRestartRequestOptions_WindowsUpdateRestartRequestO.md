# winrt::Windows::Management::Update::implementation::WindowsUpdateRestartRequestOptions::~WindowsUpdateRestartRequestOptions(void)

- ea: `0x180011a58`
- end: `0x180011b3c`
- name: `??1WindowsUpdateRestartRequestOptions@implementation@Update@Management@Windows@winrt@@UEAA@XZ`
- size: `228`
- prototype: `void __fastcall(winrt::Windows::Management::Update::implementation::WindowsUpdateRestartRequestOptions *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012050`

## callees

- `0x180008653`
- `0x18000866b`
- `0x1800117a4`
- `0x180011a58`
- `0x180016fe4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011b35`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011b35`

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
        goto LABEL_19;
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v1);
    }
    *((_QWORD *)this + 7) = 0;
  }
  if ( *((_QWORD *)this + 5) )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((char *)this + 40);
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  if ( v5 )
  {
    v6 = _InterlockedDecrement(v5 + 6);
    if ( v6 )
    {
      if ( v6 < 0 )
        goto LABEL_19;
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
    if ( !v9 )
    {
      v10 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v10, 0, (LPVOID)v8);
LABEL_16:
      *((_QWORD *)this + 3) = 0;
      goto LABEL_17;
    }
    if ( v9 >= 0 )
      goto LABEL_16;
LABEL_19:
    abort();
  }
LABEL_17:
  winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>((__int64)this);
}

```

## disassembly

```asm
0x180011a58  mov     [rsp+arg_0], rbx
0x180011a5d  mov     [rsp+arg_8], rsi
0x180011a62  push    rdi
0x180011a63  sub     rsp, 20h
0x180011a67  mov     rdi, [rcx+38h]
0x180011a6b  or      esi, 0FFFFFFFFh
0x180011a6e  mov     rbx, rcx
0x180011a71  test    rdi, rdi
0x180011a74  jz      short loc_180011AA7
0x180011a76  mov     eax, esi
0x180011a78  lock xadd [rdi+18h], eax
0x180011a7d  sub     eax, 1
0x180011a80  jnz     short loc_180011A97
0x180011a82  nop
0x180011a83  call    WINRT_IMPL_GetProcessHeap
0x180011a88  mov     rcx, rax; hHeap
0x180011a8b  mov     r8, rdi; lpMem
0x180011a8e  xor     edx, edx; dwFlags
0x180011a90  call    WINRT_IMPL_HeapFree
0x180011a95  jmp     short loc_180011A9F
0x180011a97  test    eax, eax
0x180011a99  js      loc_180011B35
0x180011a9f  mov     qword ptr [rbx+38h], 0
0x180011aa7  lea     rcx, [rbx+28h]
0x180011aab  cmp     qword ptr [rcx], 0
0x180011aaf  jz      short loc_180011AB6
0x180011ab1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011ab6  mov     rdi, [rbx+20h]
0x180011aba  test    rdi, rdi
0x180011abd  jz      short loc_180011AEC
0x180011abf  mov     eax, esi
0x180011ac1  lock xadd [rdi+18h], eax
0x180011ac6  sub     eax, 1
0x180011ac9  jnz     short loc_180011AE0
0x180011acb  nop
0x180011acc  call    WINRT_IMPL_GetProcessHeap
0x180011ad1  mov     rcx, rax; hHeap
0x180011ad4  mov     r8, rdi; lpMem
0x180011ad7  xor     edx, edx; dwFlags
0x180011ad9  call    WINRT_IMPL_HeapFree
0x180011ade  jmp     short loc_180011AE4
0x180011ae0  test    eax, eax
0x180011ae2  js      short loc_180011B35
0x180011ae4  mov     qword ptr [rbx+20h], 0
0x180011aec  mov     rdi, [rbx+18h]
0x180011af0  test    rdi, rdi
0x180011af3  jz      short loc_180011B1A
0x180011af5  lock xadd [rdi+18h], esi
0x180011afa  sub     esi, 1
0x180011afd  jnz     short loc_180011B31
0x180011aff  nop
0x180011b00  call    WINRT_IMPL_GetProcessHeap
0x180011b05  mov     rcx, rax; hHeap
0x180011b08  mov     r8, rdi; lpMem
0x180011b0b  xor     edx, edx; dwFlags
0x180011b0d  call    WINRT_IMPL_HeapFree
0x180011b12  mov     qword ptr [rbx+18h], 0
0x180011b1a  mov     rcx, rbx
0x180011b1d  mov     rbx, [rsp+28h+arg_0]
0x180011b22  mov     rsi, [rsp+28h+arg_8]
0x180011b27  add     rsp, 20h
0x180011b2b  pop     rdi
0x180011b2c  jmp     ??1?$root_implements@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>(void)
0x180011b31  test    esi, esi
0x180011b33  jns     short loc_180011B12
0x180011b35  call    cs:__imp_abort
```
