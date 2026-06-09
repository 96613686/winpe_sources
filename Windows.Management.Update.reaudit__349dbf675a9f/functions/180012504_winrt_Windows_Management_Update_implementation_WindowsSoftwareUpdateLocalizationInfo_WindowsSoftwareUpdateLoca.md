# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo::~WindowsSoftwareUpdateLocalizationInfo(void)

- ea: `0x180012504`
- end: `0x1800125b9`
- name: `??1WindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@UEAA@XZ`
- size: `181`
- prototype: `void __fastcall(winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800129f0`

## callees

- `0x180008bf4`
- `0x180008c0c`
- `0x18001234c`
- `0x180012504`
- `0x180017c3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001259b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800125ac`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001259b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800125ac`

## pseudocode

```c
void __fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo::~WindowsSoftwareUpdateLocalizationInfo(
        winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo *this)
{
  __int64 *v2; // rcx
  volatile signed __int32 *v3; // rdi
  int v4; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v6; // rdi
  int v7; // esi
  HANDLE v8; // rax

  v2 = (__int64 *)((char *)this + 48);
  if ( *v2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v2);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 5);
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
    *((_QWORD *)this + 5) = 0;
  }
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  if ( v6 )
  {
    v7 = _InterlockedDecrement(v6 + 6);
    if ( v7 )
    {
      if ( v7 < 0 )
        abort();
    }
    else
    {
      v8 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v8, 0, (LPVOID)v6);
    }
    *((_QWORD *)this + 4) = 0;
  }
  winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>((__int64)this);
}

```

## disassembly

```asm
0x180012504  mov     [rsp+arg_0], rbx
0x180012509  mov     [rsp+arg_8], rsi
0x18001250e  push    rdi
0x18001250f  sub     rsp, 20h
0x180012513  mov     rbx, rcx
0x180012516  add     rcx, 30h ; '0'
0x18001251a  cmp     qword ptr [rcx], 0
0x18001251e  jz      short loc_180012525
0x180012520  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180012525  mov     rdi, [rbx+28h]
0x180012529  or      esi, 0FFFFFFFFh
0x18001252c  test    rdi, rdi
0x18001252f  jz      short loc_180012555
0x180012531  mov     eax, esi
0x180012533  lock xadd [rdi+18h], eax
0x180012538  sub     eax, 1
0x18001253b  jnz     short loc_180012597
0x18001253d  nop
0x18001253e  call    WINRT_IMPL_GetProcessHeap
0x180012543  mov     rcx, rax; hHeap
0x180012546  mov     r8, rdi; lpMem
0x180012549  xor     edx, edx; dwFlags
0x18001254b  call    WINRT_IMPL_HeapFree
0x180012550  and     qword ptr [rbx+28h], 0
0x180012555  mov     rdi, [rbx+20h]
0x180012559  test    rdi, rdi
0x18001255c  jz      short loc_180012580
0x18001255e  lock xadd [rdi+18h], esi
0x180012563  sub     esi, 1
0x180012566  jnz     short loc_1800125A8
0x180012568  nop
0x180012569  call    WINRT_IMPL_GetProcessHeap
0x18001256e  mov     rcx, rax; hHeap
0x180012571  mov     r8, rdi; lpMem
0x180012574  xor     edx, edx; dwFlags
0x180012576  call    WINRT_IMPL_HeapFree
0x18001257b  and     qword ptr [rbx+20h], 0
0x180012580  mov     rcx, rbx
0x180012583  mov     rbx, [rsp+28h+arg_0]
0x180012588  mov     rsi, [rsp+28h+arg_8]
0x18001258d  add     rsp, 20h
0x180012591  pop     rdi
0x180012592  jmp     ??1?$root_implements@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>(void)
0x180012597  test    eax, eax
0x180012599  jns     short loc_180012550
0x18001259b  call    cs:__imp_abort
0x1800125a8  test    esi, esi
0x1800125aa  jns     short loc_18001257B
0x1800125ac  call    cs:__imp_abort
```
