# winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo::~WindowsSoftwareUpdateActionInfo(void)

- ea: `0x18001182c`
- end: `0x1800118c7`
- name: `??1WindowsSoftwareUpdateActionInfo@implementation@Update@Management@Windows@winrt@@UEAA@XZ`
- size: `155`
- prototype: `void __fastcall(winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateActionInfo *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180011d00`

## callees

- `0x180008653`
- `0x18000866b`
- `0x1800117a4`
- `0x18001182c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800118c0`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800118c0`

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
        goto LABEL_12;
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
    if ( !v6 )
    {
      v7 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v7, 0, (LPVOID)v5);
LABEL_9:
      *((_QWORD *)this + 3) = 0;
      goto LABEL_10;
    }
    if ( v6 >= 0 )
      goto LABEL_9;
LABEL_12:
    abort();
  }
LABEL_10:
  winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>((__int64)this);
}

```

## disassembly

```asm
0x18001182c  mov     [rsp+arg_0], rbx
0x180011831  mov     [rsp+arg_8], rsi
0x180011836  push    rdi
0x180011837  sub     rsp, 20h
0x18001183b  mov     rdi, [rcx+20h]
0x18001183f  or      esi, 0FFFFFFFFh
0x180011842  mov     rbx, rcx
0x180011845  test    rdi, rdi
0x180011848  jz      short loc_180011877
0x18001184a  mov     eax, esi
0x18001184c  lock xadd [rdi+18h], eax
0x180011851  sub     eax, 1
0x180011854  jnz     short loc_18001186B
0x180011856  nop
0x180011857  call    WINRT_IMPL_GetProcessHeap
0x18001185c  mov     rcx, rax; hHeap
0x18001185f  mov     r8, rdi; lpMem
0x180011862  xor     edx, edx; dwFlags
0x180011864  call    WINRT_IMPL_HeapFree
0x180011869  jmp     short loc_18001186F
0x18001186b  test    eax, eax
0x18001186d  js      short loc_1800118C0
0x18001186f  mov     qword ptr [rbx+20h], 0
0x180011877  mov     rdi, [rbx+18h]
0x18001187b  test    rdi, rdi
0x18001187e  jz      short loc_1800118A5
0x180011880  lock xadd [rdi+18h], esi
0x180011885  sub     esi, 1
0x180011888  jnz     short loc_1800118BC
0x18001188a  nop
0x18001188b  call    WINRT_IMPL_GetProcessHeap
0x180011890  mov     rcx, rax; hHeap
0x180011893  mov     r8, rdi; lpMem
0x180011896  xor     edx, edx; dwFlags
0x180011898  call    WINRT_IMPL_HeapFree
0x18001189d  mov     qword ptr [rbx+18h], 0
0x1800118a5  mov     rcx, rbx
0x1800118a8  mov     rbx, [rsp+28h+arg_0]
0x1800118ad  mov     rsi, [rsp+28h+arg_8]
0x1800118b2  add     rsp, 20h
0x1800118b6  pop     rdi
0x1800118b7  jmp     ??1?$root_implements@UWindowsSoftwareUpdateScanResult@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>::~root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateScanResult,winrt::Windows::Management::Update::WindowsSoftwareUpdateScanResult>(void)
0x1800118bc  test    esi, esi
0x1800118be  jns     short loc_18001189D
0x1800118c0  call    cs:__imp_abort
```
