# Windows::Networking::UX::CStaticIpConfig::AddGateway(HSTRING__ *,uint)

- ea: `0x180013120`
- end: `0x1800131e3`
- name: `?AddGateway@CStaticIpConfig@UX@Networking@Windows@@UEAAJPEAUHSTRING__@@I@Z`
- size: `195`
- prototype: `int(Windows::Networking::UX::CStaticIpConfig *__hidden this, HSTRING, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000e768`
- `0x180013120`
- `0x180019574`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013143`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800131cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013143`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800131cb`

## string_xrefs

- `0x180013197`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::CStaticIpConfig::AddGateway(
        Windows::Networking::UX::CStaticIpConfig *this,
        HSTRING a2,
        unsigned int a3)
{
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF

  string = 0;
  WindowsDeleteString(0);
  string = 0;
  v7 = Windows::Networking::UX::CStaticIpConfig::ShortenIpString(v6, *((_DWORD *)this + 8), a2, &string);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**((_QWORD **)this + 7) + 104LL))(*((_QWORD *)this + 7), string);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 8) + 104LL))(*((_QWORD *)this + 8), a3);
      v8 = v7;
      if ( v7 >= 0 )
      {
        v8 = 0;
        goto LABEL_9;
      }
      v9 = 133;
    }
    else
    {
      v9 = 132;
    }
  }
  else
  {
    v9 = 130;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
    (const char *)(unsigned int)v7,
    v11);
LABEL_9:
  WindowsDeleteString(string);
  return v8;
}

```

## disassembly

```asm
0x180013120  mov     [rsp+arg_8], rbx
0x180013125  mov     [rsp+arg_10], rsi
0x18001312a  push    rdi; int
0x18001312b  sub     rsp, 20h
0x18001312f  mov     esi, r8d
0x180013132  mov     rbx, rdx
0x180013135  mov     rdi, rcx
0x180013138  mov     [rsp+28h+string], 0
0x180013141  xor     ecx, ecx; string
0x180013143  call    cs:__imp_WindowsDeleteString
0x180013149  mov     [rsp+28h+string], 0
0x180013152  lea     r9, [rsp+28h+string]
0x180013157  mov     r8, rbx
0x18001315a  mov     edx, [rdi+20h]
0x18001315d  call    ?ShortenIpString@CStaticIpConfig@UX@Networking@Windows@@AEAAJW4IpFamily@234@PEAUHSTRING__@@PEAPEAU6@@Z; Windows::Networking::UX::CStaticIpConfig::ShortenIpString(Windows::Networking::UX::IpFamily,HSTRING__ *,HSTRING__ * *)
0x180013162  mov     ebx, eax
0x180013164  test    eax, eax
0x180013166  jns     short loc_18001316F
0x180013168  mov     edx, 82h
0x18001316d  jmp     short loc_18001318F
0x18001316f  mov     rcx, [rdi+38h]
0x180013173  mov     rax, [rcx]
0x180013176  mov     rdx, [rsp+28h+string]
0x18001317b  mov     rax, [rax+68h]
0x18001317f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013184  mov     ebx, eax
0x180013186  test    eax, eax
0x180013188  jns     short loc_1800131A5
0x18001318a  mov     edx, 84h; void *
0x18001318f  mov     rcx, [rsp+28h]; this
0x180013194  mov     r9d, eax; char *
0x180013197  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x18001319e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800131a3  jmp     short loc_1800131C6
0x1800131a5  mov     rcx, [rdi+40h]
0x1800131a9  mov     rax, [rcx]
0x1800131ac  mov     edx, esi
0x1800131ae  mov     rax, [rax+68h]
0x1800131b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131b7  mov     ebx, eax
0x1800131b9  test    eax, eax
0x1800131bb  jns     short loc_1800131C4
0x1800131bd  mov     edx, 85h
0x1800131c2  jmp     short loc_18001318F
0x1800131c4  xor     ebx, ebx
0x1800131c6  mov     rcx, [rsp+28h+string]; string
0x1800131cb  call    cs:__imp_WindowsDeleteString
0x1800131d1  mov     eax, ebx
0x1800131d3  mov     rbx, [rsp+28h+arg_8]
0x1800131d8  mov     rsi, [rsp+28h+arg_10]
0x1800131dd  add     rsp, 20h
0x1800131e1  pop     rdi
0x1800131e2  retn
```
