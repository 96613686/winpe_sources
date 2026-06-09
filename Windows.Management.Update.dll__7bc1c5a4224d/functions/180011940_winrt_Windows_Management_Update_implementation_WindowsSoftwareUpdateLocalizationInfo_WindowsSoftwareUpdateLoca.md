# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo::~WindowsSoftwareUpdateLocalizationInfo(void)

- ea: `0x180011940`
- end: `0x1800119ea`
- name: `??1WindowsSoftwareUpdateLocalizationInfo@implementation@Update@Management@Windows@winrt@@UEAA@XZ`
- size: `170`
- prototype: `void __fastcall(winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011e00`

## callees

- `0x180008653`
- `0x18000866b`
- `0x1800117a4`
- `0x180011940`
- `0x180016fe4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800119e3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800119e3`

## pseudocode

```c
void __fastcall winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo::~WindowsSoftwareUpdateLocalizationInfo(
        winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateLocalizationInfo *this)
{
  _QWORD *v2; // rcx
  volatile signed __int32 *v3; // rdi
  int v4; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v6; // rdi
  int v7; // esi
  HANDLE v8; // rax

  v2 = (_QWORD *)((char *)this + 48);
  if ( *v2 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v2);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 5);
  if ( v3 )
  {
    v4 = _InterlockedDecrement(v3 + 6);
    if ( v4 )
    {
      if ( v4 < 0 )
        goto LABEL_14;
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
    if ( !v7 )
    {
      v8 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v8, 0, (LPVOID)v6);
LABEL_11:
      *((_QWORD *)this + 4) = 0;
      goto LABEL_12;
    }
    if ( v7 >= 0 )
      goto LABEL_11;
LABEL_14:
    abort();
  }
LABEL_12:
  winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>((__int64)this);
}

```

## disassembly

```asm
0x180011940  mov     [rsp+arg_0], rbx
0x180011945  mov     [rsp+arg_8], rsi
0x18001194a  push    rdi
0x18001194b  sub     rsp, 20h
0x18001194f  mov     rbx, rcx
0x180011952  add     rcx, 30h ; '0'
0x180011956  cmp     qword ptr [rcx], 0
0x18001195a  jz      short loc_180011961
0x18001195c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180011961  mov     rdi, [rbx+28h]
0x180011965  or      esi, 0FFFFFFFFh
0x180011968  test    rdi, rdi
0x18001196b  jz      short loc_18001199A
0x18001196d  mov     eax, esi
0x18001196f  lock xadd [rdi+18h], eax
0x180011974  sub     eax, 1
0x180011977  jnz     short loc_18001198E
0x180011979  nop
0x18001197a  call    WINRT_IMPL_GetProcessHeap
0x18001197f  mov     rcx, rax; hHeap
0x180011982  mov     r8, rdi; lpMem
0x180011985  xor     edx, edx; dwFlags
0x180011987  call    WINRT_IMPL_HeapFree
0x18001198c  jmp     short loc_180011992
0x18001198e  test    eax, eax
0x180011990  js      short loc_1800119E3
0x180011992  mov     qword ptr [rbx+28h], 0
0x18001199a  mov     rdi, [rbx+20h]
0x18001199e  test    rdi, rdi
0x1800119a1  jz      short loc_1800119C8
0x1800119a3  lock xadd [rdi+18h], esi
0x1800119a8  sub     esi, 1
0x1800119ab  jnz     short loc_1800119DF
0x1800119ad  nop
0x1800119ae  call    WINRT_IMPL_GetProcessHeap
0x1800119b3  mov     rcx, rax; hHeap
0x1800119b6  mov     r8, rdi; lpMem
0x1800119b9  xor     edx, edx; dwFlags
0x1800119bb  call    WINRT_IMPL_HeapFree
0x1800119c0  mov     qword ptr [rbx+20h], 0
0x1800119c8  mov     rcx, rbx
0x1800119cb  mov     rbx, [rsp+28h+arg_0]
0x1800119d0  mov     rsi, [rsp+28h+arg_8]
0x1800119d5  add     rsp, 20h
0x1800119d9  pop     rdi
0x1800119da  jmp     ??1?$root_implements@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>(void)
0x1800119df  test    esi, esi
0x1800119e1  jns     short loc_1800119C0
0x1800119e3  call    cs:__imp_abort
```
