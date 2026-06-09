# _parseProfile

- ea: `0x18000bc94`
- end: `0x18000bd75`
- name: `_parseProfile`
- size: `225`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct WWAN_PROFILE *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e2f0`
- `0x18000e3f0`

## callees

- `0x18000bbd8`
- `0x18000bc94`

## pseudocode

```c
__int64 __fastcall parseProfile(struct IXMLDOMNode *a1, struct WWAN_PROFILE *a2, unsigned int a3)
{
  __int64 result; // rax

  result = _parseNode(
             a1,
             L"MBNProfileV9:MBNProfileV3",
             0,
             (unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int))parseRootNode,
             a2,
             a3,
             3u);
  if ( (_DWORD)result )
  {
    if ( (_DWORD)result == 1168 )
    {
      result = _parseNode(
                 a1,
                 L"MBNProfileV4:MBNProfileExt",
                 0,
                 (unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int))parseRootNode,
                 a2,
                 a3,
                 2u);
      if ( (_DWORD)result )
      {
        if ( (_DWORD)result == 1168 )
        {
          result = _parseNode(
                     a1,
                     L"MBNProfile:MBNProfile",
                     0,
                     (unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int))parseRootNode,
                     a2,
                     a3,
                     1u);
          if ( !(_DWORD)result )
            *((_DWORD *)a2 + 1157) = 1;
        }
      }
      else
      {
        *((_DWORD *)a2 + 1157) = 2;
      }
    }
  }
  else
  {
    *((_DWORD *)a2 + 1157) = 3;
  }
  return result;
}

```

## disassembly

```asm
0x18000bc94  mov     rax, rsp
0x18000bc97  mov     [rax+8], rbx
0x18000bc9b  mov     [rax+10h], rsi
0x18000bc9f  push    rdi
0x18000bca0  sub     rsp, 40h
0x18000bca4  mov     dword ptr [rax-18h], 3
0x18000bcab  lea     r9, _parseRootNode; unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int)
0x18000bcb2  mov     [rax-20h], r8d
0x18000bcb6  mov     edi, r8d
0x18000bcb9  mov     [rax-28h], rdx
0x18000bcbd  mov     rbx, rdx
0x18000bcc0  lea     rdx, aMbnprofilev9Mb; "MBNProfileV9:MBNProfileV3"
0x18000bcc7  xor     r8d, r8d; int
0x18000bcca  mov     rsi, rcx
0x18000bccd  call    ?_parseNode@@YAKPEAUIXMLDOMNode@@PEBGHP6AK0PEAXHK@ZPEAUWWAN_PROFILE@@HK@Z; _parseNode(IXMLDOMNode *,ushort const *,int,ulong (*)(IXMLDOMNode *,void *,int,ulong),WWAN_PROFILE *,int,ulong)
0x18000bcd2  test    eax, eax
0x18000bcd4  jnz     short loc_18000BCE5
0x18000bcd6  mov     dword ptr [rbx+1214h], 3
0x18000bce0  jmp     loc_18000BD65
0x18000bce5  cmp     eax, 490h
0x18000bcea  jnz     short loc_18000BD65
0x18000bcec  mov     [rsp+48h+var_18], 2; unsigned int
0x18000bcf4  lea     r9, _parseRootNode; unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int)
0x18000bcfb  mov     [rsp+48h+var_20], edi; int
0x18000bcff  lea     rdx, aMbnprofilev4Mb; "MBNProfileV4:MBNProfileExt"
0x18000bd06  xor     r8d, r8d; int
0x18000bd09  mov     [rsp+48h+var_28], rbx; struct WWAN_PROFILE *
0x18000bd0e  mov     rcx, rsi; struct IXMLDOMNode *
0x18000bd11  call    ?_parseNode@@YAKPEAUIXMLDOMNode@@PEBGHP6AK0PEAXHK@ZPEAUWWAN_PROFILE@@HK@Z; _parseNode(IXMLDOMNode *,ushort const *,int,ulong (*)(IXMLDOMNode *,void *,int,ulong),WWAN_PROFILE *,int,ulong)
0x18000bd16  test    eax, eax
0x18000bd18  jnz     short loc_18000BD26
0x18000bd1a  mov     dword ptr [rbx+1214h], 2
0x18000bd24  jmp     short loc_18000BD65
0x18000bd26  cmp     eax, 490h
0x18000bd2b  jnz     short loc_18000BD65
0x18000bd2d  mov     [rsp+48h+var_18], 1; unsigned int
0x18000bd35  lea     r9, _parseRootNode; unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int)
0x18000bd3c  mov     [rsp+48h+var_20], edi; int
0x18000bd40  lea     rdx, aMbnprofileMbnp; "MBNProfile:MBNProfile"
0x18000bd47  xor     r8d, r8d; int
0x18000bd4a  mov     [rsp+48h+var_28], rbx; struct WWAN_PROFILE *
0x18000bd4f  mov     rcx, rsi; struct IXMLDOMNode *
0x18000bd52  call    ?_parseNode@@YAKPEAUIXMLDOMNode@@PEBGHP6AK0PEAXHK@ZPEAUWWAN_PROFILE@@HK@Z; _parseNode(IXMLDOMNode *,ushort const *,int,ulong (*)(IXMLDOMNode *,void *,int,ulong),WWAN_PROFILE *,int,ulong)
0x18000bd57  test    eax, eax
0x18000bd59  jnz     short loc_18000BD65
0x18000bd5b  mov     dword ptr [rbx+1214h], 1
0x18000bd65  mov     rbx, [rsp+48h+arg_0]
0x18000bd6a  mov     rsi, [rsp+48h+arg_8]
0x18000bd6f  add     rsp, 40h
0x18000bd73  pop     rdi
0x18000bd74  retn
```
