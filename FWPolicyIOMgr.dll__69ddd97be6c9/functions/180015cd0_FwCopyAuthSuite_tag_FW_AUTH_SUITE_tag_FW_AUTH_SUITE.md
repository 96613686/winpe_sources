# FwCopyAuthSuite(_tag_FW_AUTH_SUITE *,_tag_FW_AUTH_SUITE *)

- ea: `0x180015cd0`
- end: `0x180015e3c`
- name: `?FwCopyAuthSuite@@YAJPEAU_tag_FW_AUTH_SUITE@@0@Z`
- size: `364`
- prototype: `__int64 __fastcall(struct _tag_FW_AUTH_SUITE *, struct _tag_FW_AUTH_SUITE *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015c50`

## callees

- `0x1800042c4`
- `0x180015cd0`
- `0x18001df4c`

## import_xrefs

- `fwbase!FwStringCopy` at `0x180015d32`
- `fwbase!FwStringCopy` at `0x180015db9`
- `fwbase!FwStringCopy` at `0x180015ded`
- `fwbase!FwStringCopy` at `0x180015d32`
- `fwbase!FwStringCopy` at `0x180015db9`
- `fwbase!FwStringCopy` at `0x180015ded`

## pseudocode

```c
__int64 __fastcall FwCopyAuthSuite(struct _tag_FW_AUTH_SUITE *a1, struct _tag_FW_AUTH_SUITE *a2)
{
  int v3; // ebx
  LPCOLESTR v5; // rcx
  __int64 v6; // rdx
  struct _tag_FW_CERT_CRITERIA *v7; // rcx

  v3 = 0;
  *(_OWORD *)a2 = 0;
  *((_QWORD *)a2 + 2) = 0;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  *((_WORD *)a2 + 2) = *((_WORD *)a1 + 2);
  if ( *(_DWORD *)a1 == 2 )
    goto LABEL_19;
  if ( *(_DWORD *)a1 == 3 )
  {
    v3 = FwStringCopy(*((_QWORD *)a1 + 1), (char *)a2 + 8);
    if ( v3 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v6 = 99;
        goto LABEL_23;
      }
    }
    return (unsigned int)v3;
  }
  if ( *(_DWORD *)a1 != 5 )
  {
    if ( *(_DWORD *)a1 != 6 )
    {
      if ( *(_DWORD *)a1 != 7 )
        return (unsigned int)v3;
      goto LABEL_6;
    }
LABEL_19:
    v3 = FwStringCopy(*((_QWORD *)a1 + 1), (char *)a2 + 8);
    if ( v3 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v6 = 100;
        goto LABEL_23;
      }
    }
    return (unsigned int)v3;
  }
LABEL_6:
  v3 = FwStringCopy(*((_QWORD *)a1 + 1), (char *)a2 + 8);
  if ( v3 >= 0 )
  {
    v7 = (struct _tag_FW_CERT_CRITERIA *)*((_QWORD *)a1 + 2);
    if ( v7 )
    {
      v3 = FwCopyCertCriteria(v7, (struct _tag_FW_CERT_CRITERIA **)a2 + 2);
      if ( v3 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v6 = 98;
          goto LABEL_23;
        }
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v6 = 97;
LABEL_23:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, (unsigned int)v3);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180015cd0  mov     [rsp+arg_0], rbx
0x180015cd5  mov     [rsp+arg_8], rsi
0x180015cda  push    rdi
0x180015cdb  sub     rsp, 20h
0x180015cdf  xor     eax, eax
0x180015ce1  mov     rsi, rdx
0x180015ce4  xorps   xmm0, xmm0
0x180015ce7  xor     ebx, ebx
0x180015ce9  movups  xmmword ptr [rdx], xmm0
0x180015cec  mov     [rdx+10h], rax
0x180015cf0  mov     rdi, rcx
0x180015cf3  mov     eax, [rcx]
0x180015cf5  mov     [rdx], eax
0x180015cf7  movzx   eax, word ptr [rcx+4]
0x180015cfb  mov     [rdx+4], ax
0x180015cff  mov     edx, [rcx]
0x180015d01  sub     edx, 2
0x180015d04  jz      loc_180015DE5
0x180015d0a  sub     edx, 1
0x180015d0d  jz      loc_180015DB1
0x180015d13  sub     edx, 2
0x180015d16  jz      short loc_180015D2A
0x180015d18  sub     edx, 1
0x180015d1b  jz      loc_180015DE5
0x180015d21  cmp     edx, 1
0x180015d24  jnz     loc_180015E2A
0x180015d2a  mov     rcx, [rcx+8]
0x180015d2e  lea     rdx, [rsi+8]
0x180015d32  call    cs:__imp_FwStringCopy
0x180015d38  mov     ebx, eax
0x180015d3a  test    eax, eax
0x180015d3c  jns     short loc_180015D69
0x180015d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d45  lea     rax, WPP_GLOBAL_Control
0x180015d4c  cmp     rcx, rax
0x180015d4f  jz      loc_180015E2A
0x180015d55  test    byte ptr [rcx+1Ch], 1
0x180015d59  jz      loc_180015E2A
0x180015d5f  mov     edx, 61h ; 'a'
0x180015d64  jmp     loc_180015E17
0x180015d69  mov     rcx, [rdi+10h]; struct _tag_FW_CERT_CRITERIA *
0x180015d6d  test    rcx, rcx
0x180015d70  jz      loc_180015E2A
0x180015d76  lea     rdx, [rsi+10h]; struct _tag_FW_CERT_CRITERIA **
0x180015d7a  call    ?FwCopyCertCriteria@@YAJPEAU_tag_FW_CERT_CRITERIA@@PEAPEAU1@@Z; FwCopyCertCriteria(_tag_FW_CERT_CRITERIA *,_tag_FW_CERT_CRITERIA * *)
0x180015d7f  mov     ebx, eax
0x180015d81  test    eax, eax
0x180015d83  jns     loc_180015E2A
0x180015d89  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d90  lea     rax, WPP_GLOBAL_Control
0x180015d97  cmp     rcx, rax
0x180015d9a  jz      loc_180015E2A
0x180015da0  test    byte ptr [rcx+1Ch], 1
0x180015da4  jz      loc_180015E2A
0x180015daa  mov     edx, 62h ; 'b'
0x180015daf  jmp     short loc_180015E17
0x180015db1  mov     rcx, [rcx+8]
0x180015db5  lea     rdx, [rsi+8]
0x180015db9  call    cs:__imp_FwStringCopy
0x180015dbf  mov     ebx, eax
0x180015dc1  test    eax, eax
0x180015dc3  jns     short loc_180015E2A
0x180015dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180015dcc  lea     rax, WPP_GLOBAL_Control
0x180015dd3  cmp     rcx, rax
0x180015dd6  jz      short loc_180015E2A
0x180015dd8  test    byte ptr [rcx+1Ch], 1
0x180015ddc  jz      short loc_180015E2A
0x180015dde  mov     edx, 63h ; 'c'
0x180015de3  jmp     short loc_180015E17
0x180015de5  mov     rcx, [rcx+8]
0x180015de9  lea     rdx, [rsi+8]
0x180015ded  call    cs:__imp_FwStringCopy
0x180015df3  mov     ebx, eax
0x180015df5  test    eax, eax
0x180015df7  jns     short loc_180015E2A
0x180015df9  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e00  lea     rax, WPP_GLOBAL_Control
0x180015e07  cmp     rcx, rax
0x180015e0a  jz      short loc_180015E2A
0x180015e0c  test    byte ptr [rcx+1Ch], 1
0x180015e10  jz      short loc_180015E2A
0x180015e12  mov     edx, 64h ; 'd'
0x180015e17  mov     rcx, [rcx+10h]
0x180015e1b  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180015e22  mov     r9d, ebx
0x180015e25  call    WPP_SF_d
0x180015e2a  mov     rsi, [rsp+28h+arg_8]
0x180015e2f  mov     eax, ebx
0x180015e31  mov     rbx, [rsp+28h+arg_0]
0x180015e36  add     rsp, 20h
0x180015e3a  pop     rdi
0x180015e3b  retn
```
