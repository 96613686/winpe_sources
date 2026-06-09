# _parseContextNode(IXMLDOMNode *,WWAN_PROFILE *,int,ulong)

- ea: `0x18000b670`
- end: `0x18000b877`
- name: `?_parseContextNode@@YAKPEAUIXMLDOMNode@@PEAUWWAN_PROFILE@@HK@Z`
- size: `519`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, struct WWAN_PROFILE *, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b4b0`
- `0x18000b670`
- `0x18000bbd8`
- `0x180012968`

## string_xrefs

- `0x18000b69d`: `MBNProfileV9:AccessString`
- `0x18000b6a9`: `MBNProfileV4:AccessString`
- `0x18000b6b0`: `MBNProfile:AccessString`
- `0x18000b742`: `MBNProfileV9:Compression`
- `0x18000b74e`: `MBNProfileV4:Compression`
- `0x18000b755`: `MBNProfile:Compression`
- `0x18000b816`: `MBNProfileV9:AuthProtocol`
- `0x18000b822`: `MBNProfileV4:AuthProtocol`
- `0x18000b829`: `MBNProfile:AuthProtocol`

## pseudocode

```c
unsigned int __fastcall _parseContextNode(struct IXMLDOMNode *a1, struct WWAN_PROFILE *a2, __int64 a3, unsigned int a4)
{
  char *v5; // r8
  const wchar_t *v8; // rdx
  unsigned int result; // eax
  const unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // rdx
  unsigned int *v13; // rdi
  const unsigned __int16 *v14; // rdx
  int v15; // [rsp+68h] [rbp+20h] BYREF

  v15 = 0;
  v5 = (char *)a2 + 3208;
  if ( a4 < 3 )
  {
    v8 = L"MBNProfileV4:AccessString";
    if ( a4 != 2 )
      v8 = L"MBNProfile:AccessString";
  }
  else
  {
    v8 = L"MBNProfileV9:AccessString";
  }
  result = getOptNodeStringValue(a1, v8, v5, 101, &v15);
  if ( !result )
  {
    if ( v15 )
      *((_DWORD *)a2 + 800) |= 1u;
    if ( a4 < 3 )
    {
      v10 = L"MBNProfileV4:UserLogonCred";
      if ( a4 != 2 )
        v10 = L"MBNProfile:UserLogonCred";
    }
    else
    {
      v10 = L"MBNProfileV9:UserLogonCred";
    }
    result = _parseNode(
               a1,
               v10,
               1,
               (unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int))parseUserLogonCredNode,
               a2,
               0,
               a4);
    if ( !result )
    {
      if ( a4 < 3 )
      {
        v11 = L"MBNProfileV4:Compression";
        if ( a4 != 2 )
          v11 = L"MBNProfile:Compression";
      }
      else
      {
        v11 = L"MBNProfileV9:Compression";
      }
      result = XcGetNodeEnumValue(
                 a1,
                 v11,
                 (const struct _XC_STRING_VALUE_MAPPING *)&_compression,
                 2u,
                 (unsigned int *)a2 + 1110,
                 1,
                 0,
                 0);
      if ( !result )
      {
        if ( a4 < 3 )
        {
          v12 = L"MBNProfileV4:IPType";
          if ( a4 != 2 )
            v12 = L"MBNProfile:IPType";
        }
        else
        {
          v12 = L"MBNProfileV9:IPType";
        }
        result = XcGetNodeEnumValue(
                   a1,
                   v12,
                   (const struct _XC_STRING_VALUE_MAPPING *)&_ipTYpe,
                   5u,
                   (unsigned int *)a2 + 1116,
                   1,
                   0,
                   &v15);
        if ( !result )
        {
          if ( v15 )
            *((_DWORD *)a2 + 800) |= 8u;
          v13 = (unsigned int *)((char *)a2 + 4444);
          if ( a4 < 3 )
          {
            v14 = L"MBNProfileV4:AuthProtocol";
            if ( a4 != 2 )
              v14 = L"MBNProfile:AuthProtocol";
          }
          else
          {
            v14 = L"MBNProfileV9:AuthProtocol";
          }
          return XcGetNodeEnumValue(a1, v14, (const struct _XC_STRING_VALUE_MAPPING *)&_authProtocol, 5u, v13, 1, 0, 0);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b670  mov     [rsp+arg_0], rbx
0x18000b675  mov     [rsp+arg_8], rsi
0x18000b67a  push    rdi
0x18000b67b  sub     rsp, 40h
0x18000b67f  mov     [rsp+48h+arg_18], 0
0x18000b687  mov     ebx, r9d
0x18000b68a  lea     r8, [rdx+0C88h]
0x18000b691  mov     rdi, rdx
0x18000b694  mov     rsi, rcx
0x18000b697  cmp     r9d, 3
0x18000b69b  jb      short loc_18000B6A6
0x18000b69d  lea     rdx, aMbnprofilev9Ac_0; "MBNProfileV9:AccessString"
0x18000b6a4  jmp     short loc_18000B6BB
0x18000b6a6  cmp     ebx, 2
0x18000b6a9  lea     rdx, aMbnprofilev4Ac_0; "MBNProfileV4:AccessString"
0x18000b6b0  lea     rax, aMbnprofileAcce_0; "MBNProfile:AccessString"
0x18000b6b7  cmovnz  rdx, rax
0x18000b6bb  lea     rax, [rsp+48h+arg_18]
0x18000b6c0  mov     r9d, 65h ; 'e'
0x18000b6c6  mov     [rsp+48h+var_28], rax
0x18000b6cb  call    _getOptNodeStringValue
0x18000b6d0  test    eax, eax
0x18000b6d2  jnz     loc_18000B867
0x18000b6d8  cmp     [rsp+48h+arg_18], eax
0x18000b6dc  jz      short loc_18000B6E5
0x18000b6de  or      dword ptr [rdi+0C80h], 1
0x18000b6e5  cmp     ebx, 3
0x18000b6e8  jb      short loc_18000B6F3
0x18000b6ea  lea     rdx, aMbnprofilev9Us; "MBNProfileV9:UserLogonCred"
0x18000b6f1  jmp     short loc_18000B708
0x18000b6f3  cmp     ebx, 2
0x18000b6f6  lea     rdx, aMbnprofilev4Us_0; "MBNProfileV4:UserLogonCred"
0x18000b6fd  lea     rax, aMbnprofileUser_0; "MBNProfile:UserLogonCred"
0x18000b704  cmovnz  rdx, rax; unsigned __int16 *
0x18000b708  mov     [rsp+48h+var_18], ebx; unsigned int
0x18000b70c  lea     r9, _parseUserLogonCredNode; unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int)
0x18000b713  mov     [rsp+48h+var_20], 0; int
0x18000b71b  mov     r8d, 1; int
0x18000b721  mov     rcx, rsi; struct IXMLDOMNode *
0x18000b724  mov     [rsp+48h+var_28], rdi; struct WWAN_PROFILE *
0x18000b729  call    ?_parseNode@@YAKPEAUIXMLDOMNode@@PEBGHP6AK0PEAXHK@ZPEAUWWAN_PROFILE@@HK@Z; _parseNode(IXMLDOMNode *,ushort const *,int,ulong (*)(IXMLDOMNode *,void *,int,ulong),WWAN_PROFILE *,int,ulong)
0x18000b72e  test    eax, eax
0x18000b730  jnz     loc_18000B867
0x18000b736  lea     rax, [rdi+1158h]
0x18000b73d  cmp     ebx, 3
0x18000b740  jb      short loc_18000B74B
0x18000b742  lea     rdx, aMbnprofilev9Co_0; "MBNProfileV9:Compression"
0x18000b749  jmp     short loc_18000B760
0x18000b74b  cmp     ebx, 2
0x18000b74e  lea     rdx, aMbnprofilev4Co_1; "MBNProfileV4:Compression"
0x18000b755  lea     rcx, aMbnprofileComp; "MBNProfile:Compression"
0x18000b75c  cmovnz  rdx, rcx; unsigned __int16 *
0x18000b760  mov     [rsp+48h+var_10], 0; int *
0x18000b769  lea     r8, ?_compression@@3QBU_XC_STRING_VALUE_MAPPING@@B; struct _XC_STRING_VALUE_MAPPING *
0x18000b770  mov     [rsp+48h+var_18], 0; unsigned int
0x18000b778  mov     r9d, 2; unsigned int
0x18000b77e  mov     [rsp+48h+var_20], 1; int
0x18000b786  mov     rcx, rsi; struct IXMLDOMNode *
0x18000b789  mov     [rsp+48h+var_28], rax; unsigned int *
0x18000b78e  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000b793  test    eax, eax
0x18000b795  jnz     loc_18000B867
0x18000b79b  lea     rax, [rdi+1170h]
0x18000b7a2  cmp     ebx, 3
0x18000b7a5  jb      short loc_18000B7B0
0x18000b7a7  lea     rdx, aMbnprofilev9Ip_5; "MBNProfileV9:IPType"
0x18000b7ae  jmp     short loc_18000B7C5
0x18000b7b0  cmp     ebx, 2
0x18000b7b3  lea     rdx, aMbnprofilev4Ip_2; "MBNProfileV4:IPType"
0x18000b7ba  lea     rcx, aMbnprofileIpty; "MBNProfile:IPType"
0x18000b7c1  cmovnz  rdx, rcx; unsigned __int16 *
0x18000b7c5  lea     rcx, [rsp+48h+arg_18]
0x18000b7ca  mov     r9d, 5; unsigned int
0x18000b7d0  mov     [rsp+48h+var_10], rcx; int *
0x18000b7d5  lea     r8, ?_ipTYpe@@3QBU_XC_STRING_VALUE_MAPPING@@B; struct _XC_STRING_VALUE_MAPPING *
0x18000b7dc  mov     [rsp+48h+var_18], 0; unsigned int
0x18000b7e4  mov     rcx, rsi; struct IXMLDOMNode *
0x18000b7e7  mov     [rsp+48h+var_20], 1; int
0x18000b7ef  mov     [rsp+48h+var_28], rax; unsigned int *
0x18000b7f4  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000b7f9  test    eax, eax
0x18000b7fb  jnz     short loc_18000B867
0x18000b7fd  cmp     [rsp+48h+arg_18], eax
0x18000b801  jz      short loc_18000B80A
0x18000b803  or      dword ptr [rdi+0C80h], 8
0x18000b80a  add     rdi, 115Ch
0x18000b811  cmp     ebx, 3
0x18000b814  jb      short loc_18000B81F
0x18000b816  lea     rdx, aMbnprofilev9Au; "MBNProfileV9:AuthProtocol"
0x18000b81d  jmp     short loc_18000B834
0x18000b81f  cmp     ebx, 2
0x18000b822  lea     rdx, aMbnprofilev4Au; "MBNProfileV4:AuthProtocol"
0x18000b829  lea     rax, aMbnprofileAuth; "MBNProfile:AuthProtocol"
0x18000b830  cmovnz  rdx, rax; unsigned __int16 *
0x18000b834  mov     [rsp+48h+var_10], 0; int *
0x18000b83d  lea     r8, ?_authProtocol@@3QBU_XC_STRING_VALUE_MAPPING@@B; struct _XC_STRING_VALUE_MAPPING *
0x18000b844  mov     [rsp+48h+var_18], 0; unsigned int
0x18000b84c  mov     r9d, 5; unsigned int
0x18000b852  mov     [rsp+48h+var_20], 1; int
0x18000b85a  mov     rcx, rsi; struct IXMLDOMNode *
0x18000b85d  mov     [rsp+48h+var_28], rdi; unsigned int *
0x18000b862  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18000b867  mov     rbx, [rsp+48h+arg_0]
0x18000b86c  mov     rsi, [rsp+48h+arg_8]
0x18000b871  add     rsp, 40h
0x18000b875  pop     rdi
0x18000b876  retn
```
