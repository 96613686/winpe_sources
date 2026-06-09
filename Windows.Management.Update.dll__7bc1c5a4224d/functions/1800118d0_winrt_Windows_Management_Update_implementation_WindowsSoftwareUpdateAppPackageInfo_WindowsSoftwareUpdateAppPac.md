# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo::~WindowsSoftwareUpdateAppPackageInfo(void)

- ea: `0x1800118d0`
- end: `0x18001193a`
- name: `??1WindowsSoftwareUpdateAppPackageInfo@implementation@Update@Management@Windows@winrt@@UEAA@XZ`
- size: `106`
- prototype: `void __fastcall(winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011d40`

## callees

- `0x180008653`
- `0x18000866b`
- `0x1800117a4`
- `0x1800118d0`
- `0x180016fe4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011933`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011933`

## pseudocode

```c
void __fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo::~WindowsSoftwareUpdateAppPackageInfo(
        winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateAppPackageInfo *this)
{
  _QWORD *v2; // rcx
  volatile signed __int32 *v3; // rdi
  int v4; // eax
  HANDLE ProcessHeap; // rax

  v2 = (_QWORD *)((char *)this + 40);
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
0x1800118d0  mov     [rsp+arg_0], rbx
0x1800118d5  push    rdi
0x1800118d6  sub     rsp, 20h
0x1800118da  mov     rbx, rcx
0x1800118dd  add     rcx, 28h ; '('
0x1800118e1  cmp     qword ptr [rcx], 0
0x1800118e5  jz      short loc_1800118EC
0x1800118e7  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800118ec  mov     rdi, [rbx+18h]
0x1800118f0  test    rdi, rdi
0x1800118f3  jz      short loc_18001191D
0x1800118f5  or      eax, 0FFFFFFFFh
0x1800118f8  lock xadd [rdi+18h], eax
0x1800118fd  sub     eax, 1
0x180011900  jnz     short loc_18001192F
0x180011902  nop
0x180011903  call    WINRT_IMPL_GetProcessHeap
0x180011908  mov     rcx, rax; hHeap
0x18001190b  mov     r8, rdi; lpMem
0x18001190e  xor     edx, edx; dwFlags
0x180011910  call    WINRT_IMPL_HeapFree
0x180011915  mov     qword ptr [rbx+18h], 0
0x18001191d  mov     rcx, rbx
0x180011920  mov     rbx, [rsp+28h+arg_0]
0x180011925  add     rsp, 20h
0x180011929  pop     rdi
0x18001192a  jmp     ??1?$root_implements@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>(void)
0x18001192f  test    eax, eax
0x180011931  jns     short loc_180011915
0x180011933  call    cs:__imp_abort
```
