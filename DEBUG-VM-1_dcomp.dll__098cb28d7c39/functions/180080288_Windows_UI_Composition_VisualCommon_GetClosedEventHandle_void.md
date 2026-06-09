# Windows::UI::Composition::VisualCommon::GetClosedEventHandle(void * *)

- ea: `0x180080288`
- end: `0x180080356`
- name: `?GetClosedEventHandle@VisualCommon@Composition@UI@Windows@@QEAAJPEAPEAX@Z`
- size: `206`
- prototype: `int(Windows::UI::Composition::VisualCommon *__hidden this, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800801f0`

## callees

- `0x18001358c`
- `0x180080288`
- `0x180081bac`
- `0x1800e55cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180080305`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180080305`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800802a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800802b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800802a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800802b3`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800802dd`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800802dd`

## string_xrefs

- `0x180080321`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtvisual.cpp`
- `0x180080339`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtvisual.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::VisualCommon::GetClosedEventHandle(
        Windows::UI::Composition::VisualCommon *this,
        void **a2)
{
  void **v2; // rdi
  HANDLE CurrentProcess; // rax
  void *v5; // rdi
  void *v6; // rbx
  HANDLE v7; // rax
  HANDLE EventW; // rax
  const char *v10; // r9
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = (void **)((char *)this + 288);
  if ( !*((_QWORD *)this + 36) )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v2,
      EventW);
    if ( !*v2 )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xC70,
               (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtvisual.cpp",
               v10);
  }
  CurrentProcess = GetCurrentProcess();
  v5 = *v2;
  v6 = CurrentProcess;
  v7 = GetCurrentProcess();
  if ( DuplicateHandle(v7, v5, v6, a2, 0, 0, 2u) )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC7C,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtvisual.cpp",
    (const char *)0x8000FFFFLL,
    dwDesiredAccess);
  return 2147549183LL;
}

```

## disassembly

```asm
0x180080288  mov     [rsp+arg_0], rbx
0x18008028d  mov     [rsp+arg_8], rsi
0x180080292  push    rdi
0x180080293  sub     rsp, 40h
0x180080297  lea     rdi, [rcx+120h]
0x18008029e  mov     rsi, rdx
0x1800802a1  cmp     qword ptr [rdi], 0
0x1800802a5  jz      short loc_1800802F9
0x1800802a7  call    cs:__imp_GetCurrentProcess
0x1800802ad  mov     rdi, [rdi]
0x1800802b0  mov     rbx, rax
0x1800802b3  call    cs:__imp_GetCurrentProcess
0x1800802b9  mov     [rsp+48h+dwOptions], 2; dwOptions
0x1800802c1  mov     r9, rsi; lpTargetHandle
0x1800802c4  mov     rcx, rax; hSourceProcessHandle
0x1800802c7  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x1800802cf  mov     r8, rbx; hTargetProcessHandle
0x1800802d2  mov     [rsp+48h+dwDesiredAccess], 0; int
0x1800802da  mov     rdx, rdi; hSourceHandle
0x1800802dd  call    cs:__imp_DuplicateHandle
0x1800802e3  test    eax, eax
0x1800802e5  jz      short loc_180080334
0x1800802e7  xor     eax, eax
0x1800802e9  mov     rbx, [rsp+48h+arg_0]
0x1800802ee  mov     rsi, [rsp+48h+arg_8]
0x1800802f3  add     rsp, 40h
0x1800802f7  pop     rdi
0x1800802f8  retn
0x1800802f9  xor     r9d, r9d; lpName
0x1800802fc  xor     r8d, r8d; bInitialState
0x1800802ff  xor     ecx, ecx; lpEventAttributes
0x180080301  lea     edx, [r9+1]; bManualReset
0x180080305  call    cs:__imp_CreateEventW
0x18008030b  mov     rdx, rax
0x18008030e  mov     rcx, rdi
0x180080311  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180080316  cmp     qword ptr [rdi], 0
0x18008031a  jnz     short loc_1800802A7
0x18008031c  mov     rcx, [rsp+48h]; this
0x180080321  lea     r8, aOnecoreuapWind_187; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180080328  mov     edx, 0C70h; void *
0x18008032d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180080332  jmp     short loc_1800802E9
0x180080334  mov     rcx, [rsp+48h]; this
0x180080339  lea     r8, aOnecoreuapWind_187; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180080340  mov     ebx, 8000FFFFh
0x180080345  mov     edx, 0C7Ch; void *
0x18008034a  mov     r9d, ebx; char *
0x18008034d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080352  mov     eax, ebx
0x180080354  jmp     short loc_1800802E9
```
