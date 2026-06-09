# MilInstrumentationBreak(ulong,bool)

- ea: `0x14000fa84`
- end: `0x14000fb2b`
- name: `?MilInstrumentationBreak@@YAXK_N@Z`
- size: `167`
- prototype: `void(unsigned int, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000f8b8`

## callees

- `0x14000daa4`
- `0x14000fa14`
- `0x14000fa84`
- `0x14000fbb0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000facc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000facc`
- `ntdll!NtQuerySystemInformation` at `0x14000faef`
- `ntdll!NtQuerySystemInformation` at `0x14000faef`

## string_xrefs

- `0x14000fb0e`: `onecoreuap\windows\dwm\common\util\utillib\debugbreak.cpp`

## pseudocode

```c
void __fastcall MilInstrumentationBreak(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  char v2; // bl
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v5; // [rsp+38h] [rbp+10h] BYREF

  LOBYTE(v5) = (_BYTE)a2;
  v2 = (char)a1;
  if ( !g_fDisableInstrumentationBreaks )
  {
    v5 = 0;
    if ( RegGetHKLMDword(a1, a2, &v5) && !v5 )
    {
      if ( (v2 & 8) == 0 || (unsigned int)IsKernelDebuggerPresent() )
        goto LABEL_10;
      if ( !IsDebuggerPresent() )
      {
        if ( !byte_14001BE72 )
          byte_14001BE72 = NtQuerySystemInformation(SystemKernelDebuggerInformation, &byte_14001BE70, 2u, 0) >= 0;
        if ( byte_14001BE70 )
LABEL_10:
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0xD6,
            (unsigned int)"onecoreuap\\windows\\dwm\\common\\util\\utillib\\debugbreak.cpp",
            (const char *)0x8007029CLL,
            v3);
      }
    }
  }
}

```

## disassembly

```asm
0x14000fa84  mov     byte ptr [rsp+arg_8], dl
0x14000fa88  push    rbx; int
0x14000fa89  sub     rsp, 20h
0x14000fa8d  cmp     cs:?g_fDisableInstrumentationBreaks@@3_NA, 0; bool g_fDisableInstrumentationBreaks
0x14000fa94  mov     ebx, ecx
0x14000fa96  jnz     loc_14000FB25
0x14000fa9c  lea     r8, [rsp+28h+arg_8]; unsigned int *
0x14000faa1  mov     [rsp+28h+arg_8], 0
0x14000faa9  call    ?RegGetHKLMDword@@YA_NQEBG0PEAK@Z; RegGetHKLMDword(ushort const * const,ushort const * const,ulong *)
0x14000faae  test    al, al
0x14000fab0  jz      short loc_14000FB25
0x14000fab2  cmp     [rsp+28h+arg_8], 0
0x14000fab7  setz    al
0x14000faba  test    al, al
0x14000fabc  jz      short loc_14000FB25
0x14000fabe  test    bl, 8
0x14000fac1  jz      short loc_14000FB09
0x14000fac3  call    ?IsKernelDebuggerPresent@@YAHXZ; IsKernelDebuggerPresent(void)
0x14000fac8  test    eax, eax
0x14000faca  jnz     short loc_14000FB09
0x14000facc  call    cs:__imp_IsDebuggerPresent
0x14000fad2  test    eax, eax
0x14000fad4  jnz     short loc_14000FB25
0x14000fad6  cmp     cs:byte_14001BE72, al
0x14000fadc  jnz     short loc_14000FB00
0x14000fade  xor     r9d, r9d; ReturnLength
0x14000fae1  lea     r8d, [rax+2]; SystemInformationLength
0x14000fae5  lea     rdx, byte_14001BE70; SystemInformation
0x14000faec  lea     ecx, [rax+23h]; SystemInformationClass
0x14000faef  call    cs:__imp_NtQuerySystemInformation
0x14000faf5  test    eax, eax
0x14000faf7  js      short loc_14000FB00
0x14000faf9  mov     cs:byte_14001BE72, 1
0x14000fb00  cmp     cs:byte_14001BE70, 0
0x14000fb07  jz      short loc_14000FB25
0x14000fb09  mov     rcx, [rsp+28h]; this
0x14000fb0e  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\common\\util"...
0x14000fb15  mov     r9d, 8007029Ch; char *
0x14000fb1b  mov     edx, 0D6h; void *
0x14000fb20  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x14000fb25  add     rsp, 20h
0x14000fb29  pop     rbx
0x14000fb2a  retn
```
