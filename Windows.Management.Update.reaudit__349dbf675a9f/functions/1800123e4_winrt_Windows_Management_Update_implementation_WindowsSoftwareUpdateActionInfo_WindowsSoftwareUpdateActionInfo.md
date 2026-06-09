# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo::~WindowsSoftwareUpdateActionInfo(void)

- ea: `0x1800123e4`
- end: `0x18001248a`
- name: `??1WindowsSoftwareUpdateActionInfo@implementation@Update@Management@Windows@winrt@@UEAA@XZ`
- size: `166`
- prototype: `void __fastcall(winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800128f0`

## callees

- `0x180008bf4`
- `0x180008c0c`
- `0x18001234c`
- `0x1800123e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001246c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001247d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001246c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001247d`

## pseudocode

```c
void __fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo::~WindowsSoftwareUpdateActionInfo(
        winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo *this)
{
  volatile signed __int32 *v1; // rdi
  int v3; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v5; // rdi
  int v6; // esi
  HANDLE v7; // rax

  v1 = (volatile signed __int32 *)*((_QWORD *)this + 4);
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
    *((_QWORD *)this + 4) = 0;
  }
  v5 = (volatile signed __int32 *)*((_QWORD *)this + 3);
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
    *((_QWORD *)this + 3) = 0;
  }
  winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>((__int64)this);
}

```

## disassembly

```asm
0x1800123e4  mov     [rsp+arg_0], rbx
0x1800123e9  mov     [rsp+arg_8], rsi
0x1800123ee  push    rdi
0x1800123ef  sub     rsp, 20h
0x1800123f3  mov     rdi, [rcx+20h]
0x1800123f7  or      esi, 0FFFFFFFFh
0x1800123fa  mov     rbx, rcx
0x1800123fd  test    rdi, rdi
0x180012400  jz      short loc_180012426
0x180012402  mov     eax, esi
0x180012404  lock xadd [rdi+18h], eax
0x180012409  sub     eax, 1
0x18001240c  jnz     short loc_180012468
0x18001240e  nop
0x18001240f  call    WINRT_IMPL_GetProcessHeap
0x180012414  mov     rcx, rax; hHeap
0x180012417  mov     r8, rdi; lpMem
0x18001241a  xor     edx, edx; dwFlags
0x18001241c  call    WINRT_IMPL_HeapFree
0x180012421  and     qword ptr [rbx+20h], 0
0x180012426  mov     rdi, [rbx+18h]
0x18001242a  test    rdi, rdi
0x18001242d  jz      short loc_180012451
0x18001242f  lock xadd [rdi+18h], esi
0x180012434  sub     esi, 1
0x180012437  jnz     short loc_180012479
0x180012439  nop
0x18001243a  call    WINRT_IMPL_GetProcessHeap
0x18001243f  mov     rcx, rax; hHeap
0x180012442  mov     r8, rdi; lpMem
0x180012445  xor     edx, edx; dwFlags
0x180012447  call    WINRT_IMPL_HeapFree
0x18001244c  and     qword ptr [rbx+18h], 0
0x180012451  mov     rcx, rbx
0x180012454  mov     rbx, [rsp+28h+arg_0]
0x180012459  mov     rsi, [rsp+28h+arg_8]
0x18001245e  add     rsp, 20h
0x180012462  pop     rdi
0x180012463  jmp     ??1?$root_implements@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>(void)
0x180012468  test    eax, eax
0x18001246a  jns     short loc_180012421
0x18001246c  call    cs:__imp_abort
0x180012479  test    esi, esi
0x18001247b  jns     short loc_18001244C
0x18001247d  call    cs:__imp_abort
```
