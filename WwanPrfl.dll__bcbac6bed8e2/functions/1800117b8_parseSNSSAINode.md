# _parseSNSSAINode

- ea: `0x1800117b8`
- end: `0x18001196c`
- name: `_parseSNSSAINode`
- size: `436`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned int *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180011974`

## callees

- `0x1800117b8`
- `0x18001288c`

## pseudocode

```c
__int64 __fastcall parseSNSSAINode(struct IXMLDOMNode *a1, unsigned int *a2, unsigned int a3, __int64 a4)
{
  const unsigned __int16 *v7; // rdx
  __int64 result; // rax
  __int64 v9; // r9
  const unsigned __int16 *v10; // rdx
  __int64 v11; // r9
  const unsigned __int16 *v12; // rdx
  __int64 v13; // r9
  const unsigned __int16 *v14; // rdx
  int v15; // [rsp+60h] [rbp+18h] BYREF

  v15 = 0;
  if ( a3 < 3 )
  {
    v7 = L"MBNProfileV4:SST";
    if ( a3 != 2 )
      v7 = L"MBNProfile:SST";
  }
  else
  {
    v7 = L"MBNProfileV9:SST";
  }
  result = XcGetNodeDWORDValue(a1, v7, a2 + 1, a4, 0xFFu, 1, 0, &v15);
  if ( !(_DWORD)result )
  {
    if ( v15 )
      *a2 |= 0x8000u;
    if ( a3 < 3 )
    {
      v10 = L"MBNProfileV4:SD";
      if ( a3 != 2 )
        v10 = L"MBNProfile:SD";
    }
    else
    {
      v10 = L"MBNProfileV9:SD";
    }
    result = XcGetNodeDWORDValue(a1, v10, a2 + 2, v9, 0xFFFFFFu, 1, 0, &v15);
    if ( !(_DWORD)result )
    {
      if ( v15 )
        *a2 |= 0x10000u;
      if ( a3 < 3 )
      {
        v12 = L"MBNProfileV4:MappedSST";
        if ( a3 != 2 )
          v12 = L"MBNProfile:MappedSST";
      }
      else
      {
        v12 = L"MBNProfileV9:MappedSST";
      }
      result = XcGetNodeDWORDValue(a1, v12, a2 + 3, v11, 0xFFu, 1, 0, &v15);
      if ( !(_DWORD)result )
      {
        if ( v15 )
          *a2 |= 0x20000u;
        if ( a3 < 3 )
        {
          v14 = L"MBNProfileV4:MappedSD";
          if ( a3 != 2 )
            v14 = L"MBNProfile:MappedSD";
        }
        else
        {
          v14 = L"MBNProfileV9:MappedSD";
        }
        result = XcGetNodeDWORDValue(a1, v14, a2 + 4, v13, 0xFFFFFFu, 1, 0, &v15);
        if ( !(_DWORD)result )
        {
          if ( v15 )
            *a2 |= 0x40000u;
          return 0;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800117b8  mov     [rsp+arg_0], rbx
0x1800117bd  mov     [rsp+arg_8], rsi
0x1800117c2  push    rdi
0x1800117c3  sub     rsp, 40h
0x1800117c7  mov     [rsp+48h+arg_10], 0
0x1800117cf  mov     edi, r8d
0x1800117d2  mov     rbx, rdx
0x1800117d5  mov     rsi, rcx
0x1800117d8  cmp     r8d, 3
0x1800117dc  jb      short loc_1800117E7
0x1800117de  lea     rdx, aMbnprofilev9Ss; "MBNProfileV9:SST"
0x1800117e5  jmp     short loc_1800117FC
0x1800117e7  cmp     edi, 2
0x1800117ea  lea     rdx, aMbnprofilev4Ss_0; "MBNProfileV4:SST"
0x1800117f1  lea     rax, aMbnprofileSst; "MBNProfile:SST"
0x1800117f8  cmovnz  rdx, rax; unsigned __int16 *
0x1800117fc  lea     rax, [rsp+48h+arg_10]
0x180011801  mov     [rsp+48h+var_10], rax; int *
0x180011806  lea     r8, [rbx+4]; unsigned int *
0x18001180a  mov     [rsp+48h+var_18], 0; unsigned int
0x180011812  mov     [rsp+48h+var_20], 1; int
0x18001181a  mov     [rsp+48h+var_28], 0FFh; unsigned int
0x180011822  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x180011827  test    eax, eax
0x180011829  jnz     loc_18001195C
0x18001182f  cmp     [rsp+48h+arg_10], eax
0x180011833  jz      short loc_180011839
0x180011835  bts     dword ptr [rbx], 0Fh
0x180011839  cmp     edi, 3
0x18001183c  jb      short loc_180011847
0x18001183e  lea     rdx, aMbnprofilev9Sd; "MBNProfileV9:SD"
0x180011845  jmp     short loc_18001185C
0x180011847  cmp     edi, 2
0x18001184a  lea     rdx, aMbnprofilev4Sd; "MBNProfileV4:SD"
0x180011851  lea     rax, aMbnprofileSd; "MBNProfile:SD"
0x180011858  cmovnz  rdx, rax; unsigned __int16 *
0x18001185c  lea     rax, [rsp+48h+arg_10]
0x180011861  mov     rcx, rsi; struct IXMLDOMNode *
0x180011864  mov     [rsp+48h+var_10], rax; int *
0x180011869  lea     r8, [rbx+8]; unsigned int *
0x18001186d  mov     [rsp+48h+var_18], 0; unsigned int
0x180011875  mov     [rsp+48h+var_20], 1; int
0x18001187d  mov     [rsp+48h+var_28], 0FFFFFFh; unsigned int
0x180011885  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x18001188a  test    eax, eax
0x18001188c  jnz     loc_18001195C
0x180011892  cmp     [rsp+48h+arg_10], eax
0x180011896  jz      short loc_18001189C
0x180011898  bts     dword ptr [rbx], 10h
0x18001189c  cmp     edi, 3
0x18001189f  jb      short loc_1800118AA
0x1800118a1  lea     rdx, aMbnprofilev9Ma_0; "MBNProfileV9:MappedSST"
0x1800118a8  jmp     short loc_1800118BF
0x1800118aa  cmp     edi, 2
0x1800118ad  lea     rdx, aMbnprofilev4Ma_1; "MBNProfileV4:MappedSST"
0x1800118b4  lea     rax, aMbnprofileMapp_0; "MBNProfile:MappedSST"
0x1800118bb  cmovnz  rdx, rax; unsigned __int16 *
0x1800118bf  lea     rax, [rsp+48h+arg_10]
0x1800118c4  mov     rcx, rsi; struct IXMLDOMNode *
0x1800118c7  mov     [rsp+48h+var_10], rax; int *
0x1800118cc  lea     r8, [rbx+0Ch]; unsigned int *
0x1800118d0  mov     [rsp+48h+var_18], 0; unsigned int
0x1800118d8  mov     [rsp+48h+var_20], 1; int
0x1800118e0  mov     [rsp+48h+var_28], 0FFh; unsigned int
0x1800118e8  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x1800118ed  test    eax, eax
0x1800118ef  jnz     short loc_18001195C
0x1800118f1  cmp     [rsp+48h+arg_10], eax
0x1800118f5  jz      short loc_1800118FB
0x1800118f7  bts     dword ptr [rbx], 11h
0x1800118fb  cmp     edi, 3
0x1800118fe  jb      short loc_180011909
0x180011900  lea     rdx, aMbnprofilev9Ma_1; "MBNProfileV9:MappedSD"
0x180011907  jmp     short loc_18001191E
0x180011909  cmp     edi, 2
0x18001190c  lea     rdx, aMbnprofilev4Ma_0; "MBNProfileV4:MappedSD"
0x180011913  lea     rax, aMbnprofileMapp; "MBNProfile:MappedSD"
0x18001191a  cmovnz  rdx, rax; unsigned __int16 *
0x18001191e  lea     rax, [rsp+48h+arg_10]
0x180011923  mov     rcx, rsi; struct IXMLDOMNode *
0x180011926  mov     [rsp+48h+var_10], rax; int *
0x18001192b  lea     r8, [rbx+10h]; unsigned int *
0x18001192f  mov     [rsp+48h+var_18], 0; unsigned int
0x180011937  mov     [rsp+48h+var_20], 1; int
0x18001193f  mov     [rsp+48h+var_28], 0FFFFFFh; unsigned int
0x180011947  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x18001194c  test    eax, eax
0x18001194e  jnz     short loc_18001195C
0x180011950  cmp     [rsp+48h+arg_10], eax
0x180011954  jz      short loc_18001195A
0x180011956  bts     dword ptr [rbx], 12h
0x18001195a  xor     eax, eax
0x18001195c  mov     rbx, [rsp+48h+arg_0]
0x180011961  mov     rsi, [rsp+48h+arg_8]
0x180011966  add     rsp, 40h
0x18001196a  pop     rdi
0x18001196b  retn
```
