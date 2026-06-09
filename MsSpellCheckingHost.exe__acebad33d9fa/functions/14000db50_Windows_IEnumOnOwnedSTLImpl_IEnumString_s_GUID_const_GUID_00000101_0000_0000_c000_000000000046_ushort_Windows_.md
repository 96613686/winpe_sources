# Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>::Skip(ulong)

- ea: `0x14000db50`
- end: `0x14000dbc8`
- name: `?Skip@?$IEnumOnOwnedSTLImpl@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Windows@@UEAAJK@Z`
- size: `120`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000db50`

## pseudocode

```c
__int64 __fastcall Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>>::Skip(
        __int64 a1,
        int a2)
{
  int v2; // r8d
  unsigned int v3; // r10d
  __int64 *v5; // rax
  __int64 *i; // rcx
  __int64 *v7; // rdx

  v2 = a2;
  v3 = 0;
  v5 = *(__int64 **)(a1 + 24);
  while ( v2 )
  {
    if ( v5 == *(__int64 **)(a1 + 8) )
    {
      v3 = 1;
      break;
    }
    --v2;
    if ( !*((_BYTE *)v5 + 25) )
    {
      i = (__int64 *)v5[2];
      if ( *((_BYTE *)i + 25) )
      {
        for ( i = (__int64 *)v5[1]; !*((_BYTE *)i + 25) && v5 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v5 = i;
      }
      else
      {
        v7 = (__int64 *)*i;
        if ( !*(_BYTE *)(*i + 25) )
        {
          do
          {
            v5 = v7;
            v7 = (__int64 *)*v7;
          }
          while ( !*((_BYTE *)v7 + 25) );
          continue;
        }
      }
      v5 = i;
    }
  }
  *(_QWORD *)(a1 + 24) = v5;
  return v3;
}

```

## disassembly

```asm
0x14000db50  xor     r11d, r11d
0x14000db53  mov     r8d, edx
0x14000db56  mov     r10d, r11d
0x14000db59  mov     r9, rcx
0x14000db5c  mov     rax, [rcx+18h]
0x14000db60  test    edx, edx
0x14000db62  jz      short loc_14000DBC0
0x14000db64  cmp     rax, [r9+8]
0x14000db68  jz      short loc_14000DBBA
0x14000db6a  dec     r8d
0x14000db6d  cmp     [rax+19h], r11b
0x14000db71  jnz     short loc_14000DBB3
0x14000db73  mov     rcx, [rax+10h]
0x14000db77  cmp     [rcx+19h], r11b
0x14000db7b  jnz     short loc_14000DB97
0x14000db7d  mov     rdx, [rcx]
0x14000db80  cmp     [rdx+19h], r11b
0x14000db84  jnz     short loc_14000DBB0
0x14000db86  mov     rcx, [rdx]
0x14000db89  mov     rax, rdx
0x14000db8c  mov     rdx, rcx
0x14000db8f  cmp     [rcx+19h], r11b
0x14000db93  jz      short loc_14000DB86
0x14000db95  jmp     short loc_14000DBB3
0x14000db97  mov     rcx, [rax+8]
0x14000db9b  jmp     short loc_14000DBAA
0x14000db9d  cmp     rax, [rcx+10h]
0x14000dba1  jnz     short loc_14000DBB0
0x14000dba3  mov     rax, rcx
0x14000dba6  mov     rcx, [rcx+8]
0x14000dbaa  cmp     [rcx+19h], r11b
0x14000dbae  jz      short loc_14000DB9D
0x14000dbb0  mov     rax, rcx
0x14000dbb3  test    r8d, r8d
0x14000dbb6  jnz     short loc_14000DB64
0x14000dbb8  jmp     short loc_14000DBC0
0x14000dbba  mov     r10d, 1
0x14000dbc0  mov     [r9+18h], rax
0x14000dbc4  mov     eax, r10d
0x14000dbc7  retn
```
