# PowerSystemStateString

- ea: `0x140012c8c`
- end: `0x140012d03`
- name: `PowerSystemStateString`
- size: `119`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000cd00`
- `0x14000ced4`
- `0x14000d1f0`
- `0x14000ec40`

## callees

- `0x140012c8c`

## pseudocode

```c
const char *__fastcall PowerSystemStateString(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx

  if ( !a1 )
    return "PowerSystemUnspecified";
  v1 = a1 - 1;
  if ( !v1 )
    return "PowerSystemWorking";
  v2 = v1 - 1;
  if ( !v2 )
    return "PowerSystemSleeping1";
  v3 = v2 - 1;
  if ( !v3 )
    return "PowerSystemSleeping2";
  v4 = v3 - 1;
  if ( !v4 )
    return "PowerSystemSleeping3";
  v5 = v4 - 1;
  if ( !v5 )
    return "PowerSystemHibernate";
  v6 = v5 - 1;
  if ( !v6 )
    return "PowerSystemShutdown";
  if ( v6 == 1 )
    return "PowerSystemMaximum";
  return "PowerSystem?????";
}

```

## disassembly

```asm
0x140012c8c  test    ecx, ecx
0x140012c8e  jz      short loc_140012CFB
0x140012c90  sub     ecx, 1
0x140012c93  jz      short loc_140012CF2
0x140012c95  sub     ecx, 1
0x140012c98  jz      short loc_140012CE9
0x140012c9a  sub     ecx, 1
0x140012c9d  jz      short loc_140012CE0
0x140012c9f  sub     ecx, 1
0x140012ca2  jz      short loc_140012CD7
0x140012ca4  sub     ecx, 1
0x140012ca7  jz      short loc_140012CCE
0x140012ca9  sub     ecx, 1
0x140012cac  jz      short loc_140012CC5
0x140012cae  cmp     ecx, 1
0x140012cb1  jz      short loc_140012CBC
0x140012cb3  lea     rax, aPowersystem; "PowerSystem?????"
0x140012cba  retn
0x140012cbc  lea     rax, aPowersystemmax; "PowerSystemMaximum"
0x140012cc3  retn
0x140012cc5  lea     rax, aPowersystemshu; "PowerSystemShutdown"
0x140012ccc  retn
0x140012cce  lea     rax, aPowersystemhib; "PowerSystemHibernate"
0x140012cd5  retn
0x140012cd7  lea     rax, aPowersystemsle_0; "PowerSystemSleeping3"
0x140012cde  retn
0x140012ce0  lea     rax, aPowersystemsle; "PowerSystemSleeping2"
0x140012ce7  retn
0x140012ce9  lea     rax, aPowersystemsle_1; "PowerSystemSleeping1"
0x140012cf0  retn
0x140012cf2  lea     rax, aPowersystemwor; "PowerSystemWorking"
0x140012cf9  retn
0x140012cfb  lea     rax, aPowersystemuns; "PowerSystemUnspecified"
0x140012d02  retn
```
