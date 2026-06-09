# ReadEnableZtdnsConfig

- ea: `0x180003674`
- end: `0x180003765`
- name: `ReadEnableZtdnsConfig`
- size: `241`
- prototype: `__int64 __fastcall(HKEY, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800039e4`

## callees

- `0x180003674`
- `0x18000f8f0`
- `0x180015008`
- `0x180015398`

## pseudocode

```c
__int64 __fastcall ReadEnableZtdnsConfig(HKEY a1, unsigned int *a2)
{
  __int64 v4; // rcx
  unsigned int *v5; // rax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qq(1026, 16, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids, a1, a2);
  if ( a2 )
  {
    v4 = 4;
    v5 = a2;
    do
    {
      *(_BYTE *)v5 = 0;
      v5 = (unsigned int *)((char *)v5 + 1);
      --v4;
    }
    while ( v4 );
  }
  if ( !a1 || !a2 )
  {
    v6 = 87;
    goto LABEL_17;
  }
  v7 = privateRegReadDwordValue(a1, L"EnableZtdns", &v10);
  v6 = v7;
  if ( v7 == 2 )
  {
    v8 = 0;
  }
  else
  {
    if ( v7 )
      goto LABEL_17;
    v8 = v10;
  }
  if ( v8 >= 3 )
  {
    v6 = 5023;
    if ( (xmmword_18001F260 & 4) == 0 )
      return v6;
    WPP_SF_d(1026, 17, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids, 5023);
  }
  else
  {
    v6 = 0;
    *a2 = v8;
  }
LABEL_17:
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 18, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180003674  mov     [rsp+arg_8], rbx
0x180003679  push    rdi
0x18000367a  sub     rsp, 30h
0x18000367e  mov     rdi, rdx
0x180003681  mov     [rsp+38h+arg_0], 0
0x180003689  mov     rbx, rcx
0x18000368c  test    byte ptr cs:xmmword_18001F260, 4
0x180003693  jz      short loc_1800036B3
0x180003695  mov     edx, 10h
0x18000369a  mov     [rsp+38h+var_18], rdi
0x18000369f  mov     ecx, 402h
0x1800036a4  lea     r8, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x1800036ab  mov     r9, rbx
0x1800036ae  call    WPP_SF_qq
0x1800036b3  test    rdi, rdi
0x1800036b6  jz      short loc_1800036CC
0x1800036b8  mov     ecx, 4
0x1800036bd  mov     rax, rdi
0x1800036c0  mov     byte ptr [rax], 0
0x1800036c3  inc     rax
0x1800036c6  sub     rcx, 1
0x1800036ca  jnz     short loc_1800036C0
0x1800036cc  test    rbx, rbx
0x1800036cf  jnz     short loc_1800036D8
0x1800036d1  mov     ebx, 57h ; 'W'
0x1800036d6  jmp     short loc_180003736
0x1800036d8  test    rdi, rdi
0x1800036db  jz      short loc_1800036D1
0x1800036dd  lea     r8, [rsp+38h+arg_0]
0x1800036e2  mov     rcx, rbx
0x1800036e5  lea     rdx, aEnableztdns; "EnableZtdns"
0x1800036ec  call    privateRegReadDwordValue
0x1800036f1  mov     ebx, eax
0x1800036f3  cmp     eax, 2
0x1800036f6  jnz     short loc_1800036FC
0x1800036f8  xor     eax, eax
0x1800036fa  jmp     short loc_180003704
0x1800036fc  test    eax, eax
0x1800036fe  jnz     short loc_180003736
0x180003700  mov     eax, [rsp+38h+arg_0]
0x180003704  cmp     eax, 3
0x180003707  jnb     short loc_18000370F
0x180003709  xor     ebx, ebx
0x18000370b  mov     [rdi], eax
0x18000370d  jmp     short loc_180003736
0x18000370f  mov     ebx, 139Fh
0x180003714  test    byte ptr cs:xmmword_18001F260, 4
0x18000371b  jz      short loc_180003758
0x18000371d  mov     edx, 11h
0x180003722  lea     r8, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x180003729  mov     ecx, 402h
0x18000372e  mov     r9d, ebx
0x180003731  call    WPP_SF_d
0x180003736  test    byte ptr cs:xmmword_18001F260, 4
0x18000373d  jz      short loc_180003758
0x18000373f  mov     edx, 12h
0x180003744  lea     r8, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x18000374b  mov     ecx, 402h
0x180003750  mov     r9d, ebx
0x180003753  call    WPP_SF_d
0x180003758  mov     eax, ebx
0x18000375a  mov     rbx, [rsp+38h+arg_8]
0x18000375f  add     rsp, 30h
0x180003763  pop     rdi
0x180003764  retn
```
