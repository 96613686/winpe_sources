# OpenKey(HKEY__ *,wchar_t const *,RegistryKey::Allow,HKEY__ * *)

- ea: `0x18006a1c0`
- end: `0x18006a26b`
- name: `?OpenKey@@YAJPEAUHKEY__@@PEB_WW4Allow@RegistryKey@@PEAPEAU1@@Z`
- size: `171`
- prototype: `int __high(HKEY, const wchar_t *, enum RegistryKey::Allow, HKEY *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180068da0`
- `0x180069da8`
- `0x180069df8`

## callees

- `0x1800217ac`
- `0x18002faf0`
- `0x18006a1c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006a228`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006a228`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006a20a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006a20a`

## pseudocode

```c
LSTATUS __fastcall OpenKey(HKEY a1, const WCHAR *a2, char a3, HKEY *a4)
{
  LSTATUS result; // eax
  unsigned int v6; // edx
  int v7; // [rsp+70h] [rbp+18h] BYREF

  *a4 = 0;
  if ( (a3 & 2) != 0 )
  {
    v7 = 0;
    result = RegCreateKeyExW(a1, a2, 0, 0, 0, 0x2001Fu, 0, a4, (LPDWORD)&v7);
  }
  else
  {
    result = RegOpenKeyExW(a1, a2, 0, 0x20019u, a4);
  }
  if ( result && (a3 & 1) == 0 )
  {
    if ( result > 0 )
      v6 = (unsigned __int16)result | 0x80070000;
    else
      v6 = result;
    Exception::Exception((Exception *)&v7, v6, result);
    LogAndThrow<OSException>(&v7, 6776178, 102);
  }
  return result;
}

```

## disassembly

```asm
0x18006a1c0  mov     r11, rsp
0x18006a1c3  push    rbx
0x18006a1c4  sub     rsp, 50h
0x18006a1c8  mov     qword ptr [r9], 0
0x18006a1cf  mov     ebx, r8d
0x18006a1d2  test    r8b, 2
0x18006a1d6  jz      short loc_18006A21A
0x18006a1d8  lea     rax, [r11+18h]
0x18006a1dc  mov     [rsp+58h+arg_10], 0
0x18006a1e4  mov     [r11-18h], rax
0x18006a1e8  xor     r8d, r8d; Reserved
0x18006a1eb  mov     [r11-20h], r9
0x18006a1ef  xor     r9d, r9d; lpClass
0x18006a1f2  mov     qword ptr [r11-28h], 0
0x18006a1fa  mov     [rsp+58h+samDesired], 2001Fh; samDesired
0x18006a202  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18006a20a  call    cs:__imp_RegCreateKeyExW
0x18006a210  test    eax, eax
0x18006a212  jnz     short loc_18006A264
0x18006a214  add     rsp, 50h
0x18006a218  pop     rbx
0x18006a219  retn
0x18006a21a  mov     qword ptr [rsp+58h+dwOptions], r9; phkResult
0x18006a21f  xor     r8d, r8d; ulOptions
0x18006a222  mov     r9d, 20019h; samDesired
0x18006a228  call    cs:__imp_RegOpenKeyExW
0x18006a22e  jmp     short loc_18006A210
0x18006a230  test    eax, eax
0x18006a232  jg      short loc_18006A259
0x18006a234  mov     edx, eax; int
0x18006a236  mov     r8d, eax; unsigned int
0x18006a239  lea     rcx, [rsp+58h+arg_10]; this
0x18006a23e  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18006a243  mov     edx, 676572h
0x18006a248  lea     rcx, [rsp+58h+arg_10]
0x18006a24d  mov     r8d, 66h ; 'f'
0x18006a253  call    ??$LogAndThrow@VOSException@@@@YAXAEBVOSException@@VEventTag@@I@Z; LogAndThrow<OSException>(OSException const &,EventTag,uint)
0x18006a259  movzx   edx, ax
0x18006a25c  or      edx, 80070000h
0x18006a262  jmp     short loc_18006A236
0x18006a264  test    bl, 1
0x18006a267  jnz     short loc_18006A214
0x18006a269  jmp     short loc_18006A230
```
