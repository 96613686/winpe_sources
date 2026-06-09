# ZtNotifyDnscache(_ZTDNS_SETTINGS_TYPE,_DNS_ZT_SETTINGS *,_DNS_ZT_SETTINGS_STATE *)

- ea: `0x18000482c`
- end: `0x1800048e9`
- name: `?ZtNotifyDnscache@@YAJW4_ZTDNS_SETTINGS_TYPE@@PEAU_DNS_ZT_SETTINGS@@PEAU_DNS_ZT_SETTINGS_STATE@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800044e4`
- `0x1800052c4`

## callees

- `0x18000482c`
- `0x180015008`
- `0x180015040`

## import_xrefs

- `DNSAPI!DnsZtNotifyDnscache` at `0x180004887`
- `DNSAPI!DnsZtNotifyDnscache` at `0x180004887`

## pseudocode

```c
__int64 __fastcall ZtNotifyDnscache(unsigned int a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // eax

  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_dqq(1026, 10, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, a1, a2, a3);
  if ( a2 && a3 )
  {
    v7 = DnsZtNotifyDnscache(a1, a2, a3);
    v6 = v7;
    if ( v7 )
    {
      if ( (xmmword_18001F260 & 4) == 0 )
        return v6;
      WPP_SF_d(1026, 11, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, v7);
    }
  }
  else
  {
    v6 = 87;
  }
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 12, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000482c  mov     rax, rsp
0x18000482f  mov     [rax+8], rbx
0x180004833  mov     [rax+10h], rsi
0x180004837  push    rdi
0x180004838  sub     rsp, 30h
0x18000483c  mov     rbx, r8
0x18000483f  mov     rdi, rdx
0x180004842  mov     esi, ecx
0x180004844  test    byte ptr cs:xmmword_18001F260, 4
0x18000484b  jz      short loc_18000486E
0x18000484d  mov     [rax-10h], rbx
0x180004851  lea     r8, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids
0x180004858  mov     edx, 0Ah
0x18000485d  mov     [rax-18h], rdi
0x180004861  mov     ecx, 402h
0x180004866  mov     r9d, esi
0x180004869  call    WPP_SF_dqq
0x18000486e  test    rdi, rdi
0x180004871  jnz     short loc_18000487A
0x180004873  mov     ebx, 57h ; 'W'
0x180004878  jmp     short loc_1800048B5
0x18000487a  test    rbx, rbx
0x18000487d  jz      short loc_180004873
0x18000487f  mov     r8, rbx
0x180004882  mov     rdx, rdi
0x180004885  mov     ecx, esi
0x180004887  call    cs:__imp_DnsZtNotifyDnscache
0x18000488d  mov     ebx, eax
0x18000488f  test    eax, eax
0x180004891  jz      short loc_1800048B5
0x180004893  test    byte ptr cs:xmmword_18001F260, 4
0x18000489a  jz      short loc_1800048D7
0x18000489c  mov     edx, 0Bh
0x1800048a1  lea     r8, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids
0x1800048a8  mov     ecx, 402h
0x1800048ad  mov     r9d, eax
0x1800048b0  call    WPP_SF_d
0x1800048b5  test    byte ptr cs:xmmword_18001F260, 4
0x1800048bc  jz      short loc_1800048D7
0x1800048be  mov     edx, 0Ch
0x1800048c3  lea     r8, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids
0x1800048ca  mov     ecx, 402h
0x1800048cf  mov     r9d, ebx
0x1800048d2  call    WPP_SF_d
0x1800048d7  mov     rsi, [rsp+38h+arg_8]
0x1800048dc  mov     eax, ebx
0x1800048de  mov     rbx, [rsp+38h+arg_0]
0x1800048e3  add     rsp, 30h
0x1800048e7  pop     rdi
0x1800048e8  retn
```
