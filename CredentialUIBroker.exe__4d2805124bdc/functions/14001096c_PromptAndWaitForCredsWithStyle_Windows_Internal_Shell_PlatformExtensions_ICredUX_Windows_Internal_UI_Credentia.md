# PromptAndWaitForCredsWithStyle(Windows::Internal::Shell::PlatformExtensions::ICredUX *,Windows::Internal::UI::Credentials::Controller::CredUIStyle,Windows::Internal::UI::Credentials::Controller::ICredUXExtension *,Windows::Internal::UI::Credentials::Controller::IConsentUXContext *,Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt *,ulong,_CREDUI_CONTEXT const *,CREDUI_INFO_INTERNAL *,ulong,ulong *,void const *,ulong,void * *,ulong *,int *,ulong,ulong *)

- ea: `0x14001096c`
- end: `0x140010a82`
- name: `?PromptAndWaitForCredsWithStyle@@YAJPEAUICredUX@PlatformExtensions@Shell@Internal@Windows@@W4CredUIStyle@Controller@Credentials@UI@45@PEAUICredUXExtension@78945@PEAUIConsentUXContext@78945@PEAUICredUXSecurePrompt@78945@KPEBU_CREDUI_CONTEXT@@PEAUCREDUI_INFO_INTERNAL@@KPEAKPEBXKPEAPEAX7PEAHK7@Z`
- size: `278`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, _QWORD *, _DWORD *, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400137d4`

## callees

- `0x14001096c`
- `0x1400111ac`
- `0x1400136fc`

## string_xrefs

- `0x140010a60`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall PromptAndWaitForCredsWithStyle(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        _QWORD *a13,
        _DWORD *a14,
        __int64 a15,
        __int64 a16,
        _DWORD *a17)
{
  int v17; // ebx
  __int64 v19; // rdx
  int v20; // [rsp+20h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  *a17 = 1237;
  if ( a13 && a14 )
  {
    *a13 = 0;
    *a14 = 0;
    v17 = PromptInternal();
    *a17 = (unsigned __int16)v17;
    if ( v17 >= 0 )
      return 0;
    v19 = 970;
  }
  else
  {
    v17 = -2147024809;
    v19 = 956;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v19,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)v17,
    v20);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x14001096c  mov     r11, rsp
0x14001096f  mov     [r11+8], rbx
0x140010973  push    rdi
0x140010974  sub     rsp, 90h
0x14001097b  mov     rdi, [rsp+98h+arg_80]
0x140010983  mov     r9, [rsp+98h+arg_60]
0x14001098b  mov     dword ptr [rdi], 4D5h
0x140010991  test    r9, r9
0x140010994  jz      loc_140010A4E
0x14001099a  mov     r8, [rsp+98h+arg_68]
0x1400109a2  test    r8, r8
0x1400109a5  jz      loc_140010A4E
0x1400109ab  lea     rax, [r11+30h]
0x1400109af  mov     qword ptr [r9], 0
0x1400109b6  mov     [r11-18h], rax
0x1400109ba  mov     eax, [rsp+98h+arg_78]
0x1400109c1  mov     [rsp+98h+var_20], eax
0x1400109c5  mov     rax, [rsp+98h+arg_70]
0x1400109cd  mov     [r11-28h], rax
0x1400109d1  mov     eax, [rsp+98h+arg_58]
0x1400109d8  mov     [r11-30h], r8
0x1400109dc  mov     [r11-38h], r9
0x1400109e0  mov     [rsp+98h+var_40], eax
0x1400109e4  mov     rax, [rsp+98h+arg_50]
0x1400109ec  mov     [r11-48h], rax
0x1400109f0  mov     rax, [rsp+98h+arg_48]
0x1400109f8  mov     [r11-50h], rax
0x1400109fc  mov     eax, [rsp+98h+arg_40]
0x140010a03  mov     [rsp+98h+var_58], eax
0x140010a07  mov     rax, [rsp+98h+arg_38]
0x140010a0f  mov     [r11-60h], rax
0x140010a13  mov     dword ptr [r8], 0
0x140010a1a  mov     byte ptr [r11+30h], 0
0x140010a1f  call    ?PromptInternal@@YAJPEAUICredUX@PlatformExtensions@Shell@Internal@Windows@@W4CredUIStyle@Controller@Credentials@UI@45@PEAUICredUXExtension@78945@PEAUIConsentUXContext@78945@PEAUICredUXSecurePrompt@78945@KPEBU_CREDUI_CONTEXT@@PEAUCREDUI_INFO_INTERNAL@@KPEAKPEBXKPEAPEAX7PEAHKPEA_N@Z; PromptInternal(Windows::Internal::Shell::PlatformExtensions::ICredUX *,Windows::Internal::UI::Credentials::Controller::CredUIStyle,Windows::Internal::UI::Credentials::Controller::ICredUXExtension *,Windows::Internal::UI::Credentials::Controller::IConsentUXContext *,Windows::Internal::UI::Credentials::Controller::ICredUXSecurePrompt *,ulong,_CREDUI_CONTEXT const *,CREDUI_INFO_INTERNAL *,ulong,ulong *,void const *,ulong,void * *,ulong *,int *,ulong,bool *)
0x140010a24  mov     ebx, eax
0x140010a26  test    eax, eax
0x140010a28  js      short loc_140010A3E
0x140010a2a  cmp     [rsp+98h+arg_28], 0
0x140010a32  jz      short loc_140010A3E
0x140010a34  mov     dword ptr [rdi], 4C7h
0x140010a3a  xor     eax, eax
0x140010a3c  jmp     short loc_140010A71
0x140010a3e  movzx   eax, bx
0x140010a41  mov     [rdi], eax
0x140010a43  test    ebx, ebx
0x140010a45  jns     short loc_140010A3A
0x140010a47  mov     edx, 3CAh
0x140010a4c  jmp     short loc_140010A58
0x140010a4e  mov     ebx, 80070057h
0x140010a53  mov     edx, 3BCh; void *
0x140010a58  mov     rcx, [rsp+98h]; this
0x140010a60  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x140010a67  mov     r9d, ebx; char *
0x140010a6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010a6f  mov     eax, ebx
0x140010a71  mov     rbx, [rsp+98h+arg_0]
0x140010a79  add     rsp, 90h
0x140010a80  pop     rdi
0x140010a81  retn
```
