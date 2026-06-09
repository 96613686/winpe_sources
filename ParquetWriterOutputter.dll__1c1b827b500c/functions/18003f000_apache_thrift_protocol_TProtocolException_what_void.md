# apache::thrift::protocol::TProtocolException::what(void)

- ea: `0x18003f000`
- end: `0x18003f06a`
- name: `?what@TProtocolException@protocol@thrift@apache@@UEBAPEBDXZ`
- size: `106`
- prototype: `const char *__fastcall(apache::thrift::protocol::TProtocolException *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003f000`

## string_xrefs

- `0x18003f023`: `TProtocolException: Unknown protocol exception`
- `0x18003f02b`: `TProtocolException: Invalid data`
- `0x18003f033`: `TProtocolException: Negative size`
- `0x18003f03b`: `TProtocolException: Exceeded size limit`
- `0x18003f043`: `TProtocolException: Invalid version`
- `0x18003f04b`: `TProtocolException: Not implemented`
- `0x18003f053`: `TProtocolException: (Invalid exception type)`

## pseudocode

```c
const char *__fastcall apache::thrift::protocol::TProtocolException::what(
        apache::thrift::protocol::TProtocolException *this)
{
  const char *result; // rax

  if ( *((_QWORD *)this + 5) )
  {
    result = (char *)this + 24;
    if ( *((_QWORD *)this + 6) >= 0x10u )
      return *(const char **)result;
  }
  else
  {
    switch ( *((_DWORD *)this + 14) )
    {
      case 0:
        result = "TProtocolException: Unknown protocol exception";
        break;
      case 1:
        result = "TProtocolException: Invalid data";
        break;
      case 2:
        result = "TProtocolException: Negative size";
        break;
      case 3:
        result = "TProtocolException: Exceeded size limit";
        break;
      case 4:
        result = "TProtocolException: Invalid version";
        break;
      case 5:
        result = "TProtocolException: Not implemented";
        break;
      default:
        result = "TProtocolException: (Invalid exception type)";
        break;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003f000  cmp     qword ptr [rcx+28h], 0
0x18003f005  jnz     short loc_18003F05B
0x18003f007  movsxd  rax, dword ptr [rcx+38h]
0x18003f00b  cmp     eax, 5; switch 6 cases
0x18003f00e  ja      short def_18003F021; jumptable 000000018003F021 default case
0x18003f010  lea     rdx, cs:180000000h
0x18003f017  mov     ecx, ds:(jpt_18003F021 - 180000000h)[rdx+rax*4]
0x18003f01e  add     rcx, rdx
0x18003f021  jmp     rcx; switch jump
0x18003f023  lea     rax, aTprotocolexcep; jumptable 000000018003F021 case 0
0x18003f02a  retn
0x18003f02b  lea     rax, aTprotocolexcep_0; jumptable 000000018003F021 case 1
0x18003f032  retn
0x18003f033  lea     rax, aTprotocolexcep_4; jumptable 000000018003F021 case 2
0x18003f03a  retn
0x18003f03b  lea     rax, aTprotocolexcep_3; jumptable 000000018003F021 case 3
0x18003f042  retn
0x18003f043  lea     rax, aTprotocolexcep_5; jumptable 000000018003F021 case 4
0x18003f04a  retn
0x18003f04b  lea     rax, aTprotocolexcep_2; jumptable 000000018003F021 case 5
0x18003f052  retn
0x18003f053  lea     rax, aTprotocolexcep_1; jumptable 000000018003F021 default case
0x18003f05a  retn
0x18003f05b  cmp     qword ptr [rcx+30h], 10h
0x18003f060  lea     rax, [rcx+18h]
0x18003f064  jb      short locret_18003F069
0x18003f066  mov     rax, [rax]
0x18003f069  retn
```
