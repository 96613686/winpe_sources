# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo::~WindowsSoftwareUpdateAppPackageInfo(void)

- ea: `0x180012490`
- end: `0x1800124fd`
- name: `??1WindowsSoftwareUpdateAppPackageInfo@implementation@Update@Management@Windows@winrt@@UEAA@XZ`
- size: `109`
- prototype: `void __fastcall(winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012930`

## callees

- `0x180008bf4`
- `0x180008c0c`
- `0x18001234c`
- `0x180012490`
- `0x180017c3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800124f0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800124f0`

## pseudocode

```c
void __fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo::~WindowsSoftwareUpdateAppPackageInfo(
        winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo *this)
{
  __int64 *v2; // rcx
  volatile signed __int32 *v3; // rdi
  int v4; // eax
  HANDLE ProcessHeap; // rax

  v2 = (__int64 *)((char *)this + 40);
  if ( *v2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v2);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  if ( v3 )
  {
    v4 = _InterlockedDecrement(v3 + 6);
    if ( v4 )
    {
      if ( v4 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v3);
    }
    *((_QWORD *)this + 3) = 0;
  }
  winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>((__int64)this);
}

```

## disassembly

```asm
0x180012490  mov     [rsp+arg_0], rbx
0x180012495  push    rdi
0x180012496  sub     rsp, 20h
0x18001249a  mov     rbx, rcx
0x18001249d  add     rcx, 28h ; '('
0x1800124a1  cmp     qword ptr [rcx], 0
0x1800124a5  jz      short loc_1800124AC
0x1800124a7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800124ac  mov     rdi, [rbx+18h]
0x1800124b0  test    rdi, rdi
0x1800124b3  jz      short loc_1800124DA
0x1800124b5  or      eax, 0FFFFFFFFh
0x1800124b8  lock xadd [rdi+18h], eax
0x1800124bd  sub     eax, 1
0x1800124c0  jnz     short loc_1800124EC
0x1800124c2  nop
0x1800124c3  call    WINRT_IMPL_GetProcessHeap
0x1800124c8  mov     rcx, rax; hHeap
0x1800124cb  mov     r8, rdi; lpMem
0x1800124ce  xor     edx, edx; dwFlags
0x1800124d0  call    WINRT_IMPL_HeapFree
0x1800124d5  and     qword ptr [rbx+18h], 0
0x1800124da  mov     rcx, rbx
0x1800124dd  mov     rbx, [rsp+28h+arg_0]
0x1800124e2  add     rsp, 20h
0x1800124e6  pop     rdi
0x1800124e7  jmp     ??1?$root_implements@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>(void)
0x1800124ec  test    eax, eax
0x1800124ee  jns     short loc_1800124D5
0x1800124f0  call    cs:__imp_abort
```
