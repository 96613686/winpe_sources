# CommonUtil::UtilRegGetValueDword(HKEY__ *,wchar_t const *,ulong *)

- ea: `0x140004f34`
- end: `0x140004fac`
- name: `?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAK@Z`
- size: `120`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, HKEY, const wchar_t *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400029b0`
- `0x140002af0`

## callees

- `0x140004dc0`
- `0x140004f34`
- `0x140005c20`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegGetValueDword(CommonUtil *this, const WCHAR *a2, BYTE *a3, unsigned int *a4)
{
  int Value; // eax
  int v5; // edx
  unsigned int v6; // ecx
  __int64 result; // rax
  DWORD v8; // [rsp+30h] [rbp-28h] BYREF
  __int64 v9; // [rsp+38h] [rbp-20h] BYREF

  v8 = 0;
  v9 = 4;
  Value = CommonUtil::UtilRegGetValue(this, a2, &v8, (unsigned int *)&v9, a3);
  v5 = Value;
  if ( Value == -2147024662 )
    return 2147944029LL;
  v6 = (unsigned int)Value >> 31;
  if ( Value >= 0 && v8 != 4 )
    return 2147944029LL;
  result = 2147942402LL;
  if ( v5 != -2147024894 )
    return v5 & (unsigned int)-((_BYTE)v6 != 0);
  return result;
}

```

## disassembly

```asm
0x140004f34  mov     r11, rsp
0x140004f37  sub     rsp, 58h
0x140004f3b  mov     rax, cs:__security_cookie
0x140004f42  xor     rax, rsp
0x140004f45  mov     [rsp+58h+var_18], rax
0x140004f4a  mov     [r11-38h], r8
0x140004f4e  lea     r9, [r11-20h]; unsigned int *
0x140004f52  lea     r8, [r11-28h]; wchar_t *
0x140004f56  mov     [rsp+58h+var_28], 0
0x140004f5e  mov     qword ptr [r11-20h], 4
0x140004f66  call    ?UtilRegGetValue@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAKPEA_KPEAX@Z; CommonUtil::UtilRegGetValue(HKEY__ *,wchar_t const *,ulong *,unsigned __int64 *,void *)
0x140004f6b  mov     edx, eax
0x140004f6d  cmp     eax, 800700EAh
0x140004f72  jz      short loc_140004F95
0x140004f74  mov     ecx, eax
0x140004f76  shr     ecx, 1Fh
0x140004f79  test    cl, cl
0x140004f7b  jnz     short loc_140004F84
0x140004f7d  cmp     [rsp+58h+var_28], 4
0x140004f82  jnz     short loc_140004F95
0x140004f84  mov     eax, 80070002h
0x140004f89  cmp     edx, eax
0x140004f8b  jz      short loc_140004F9A
0x140004f8d  neg     cl
0x140004f8f  sbb     eax, eax
0x140004f91  and     eax, edx
0x140004f93  jmp     short loc_140004F9A
0x140004f95  mov     eax, 8007065Dh
0x140004f9a  mov     rcx, [rsp+58h+var_18]
0x140004f9f  xor     rcx, rsp; StackCookie
0x140004fa2  call    __security_check_cookie
0x140004fa7  add     rsp, 58h
0x140004fab  retn
```
