# ProfileRegReadValue(HKEY__ *,ushort const *,ushort *,int)

- ea: `0x18006aefc`
- end: `0x18006af96`
- name: `?ProfileRegReadValue@@YAJPEAUHKEY__@@PEBGPEAGH@Z`
- size: `154`
- prototype: `int(HKEY, const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180068590`
- `0x180069a9c`

## callees

- `0x18006aefc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006af3f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006af3f`
- `MFPlat!MFTraceError` at `0x18006af88`
- `MFPlat!MFTraceError` at `0x18006af88`

## string_xrefs

- `0x18006af73`: `ProfileRegReadValue`

## pseudocode

```c
__int64 __fastcall ProfileRegReadValue(HKEY a1, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  LSTATUS ValueW; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  DWORD v7[6]; // [rsp+40h] [rbp-18h] BYREF

  v7[0] = 260;
  if ( (unsigned __int64)a1 - 1 > 0xFFFFFFFFFFFFFFFDuLL || !a2 || !a3 )
  {
    v4 = -2147024809;
    v5 = 810;
LABEL_10:
    MFTraceError("avcore\\mf\\core\\mediasource\\profiles\\profileparser.cpp", v5, "ProfileRegReadValue", 0, v4, 1);
    return v4;
  }
  ValueW = RegGetValueW(a1, 0, a2, 2u, 0, a3, v7);
  v4 = ValueW;
  if ( ValueW )
  {
    if ( ValueW > 0 )
      v4 = (unsigned __int16)ValueW | 0x80070000;
    v5 = 818;
    goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x18006aefc  mov     r11, rsp
0x18006aeff  push    rbx
0x18006af00  sub     rsp, 50h
0x18006af04  lea     rax, [rcx-1]
0x18006af08  mov     [rsp+58h+var_18], 104h
0x18006af10  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006af14  ja      short loc_18006AF61
0x18006af16  test    rdx, rdx
0x18006af19  jz      short loc_18006AF61
0x18006af1b  test    r8, r8
0x18006af1e  jz      short loc_18006AF61
0x18006af20  lea     rax, [r11-18h]
0x18006af24  mov     r9d, 2; dwFlags
0x18006af2a  mov     [r11-28h], rax
0x18006af2e  mov     [r11-30h], r8
0x18006af32  mov     r8, rdx; lpValue
0x18006af35  xor     edx, edx; lpSubKey
0x18006af37  mov     qword ptr [r11-38h], 0
0x18006af3f  call    cs:__imp_RegGetValueW
0x18006af45  mov     ebx, eax
0x18006af47  test    eax, eax
0x18006af49  jz      short loc_18006AF5D
0x18006af4b  jle     short loc_18006AF56
0x18006af4d  movzx   ebx, ax
0x18006af50  or      ebx, 80070000h
0x18006af56  mov     edx, 332h
0x18006af5b  jmp     short loc_18006AF6B
0x18006af5d  xor     ebx, ebx
0x18006af5f  jmp     short loc_18006AF8E
0x18006af61  mov     ebx, 80070057h
0x18006af66  mov     edx, 32Ah
0x18006af6b  mov     [rsp+58h+var_30], 1
0x18006af73  lea     r8, aProfileregread; "ProfileRegReadValue"
0x18006af7a  xor     r9d, r9d
0x18006af7d  mov     [rsp+58h+var_38], ebx
0x18006af81  lea     rcx, aAvcoreMfCoreMe; "avcore\\mf\\core\\mediasource\\profiles"...
0x18006af88  call    cs:__imp_MFTraceError
0x18006af8e  mov     eax, ebx
0x18006af90  add     rsp, 50h
0x18006af94  pop     rbx
0x18006af95  retn
```
