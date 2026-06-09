# CommonUtil::UtilDuplicateSid(void * *,void *)

- ea: `0x1800df368`
- end: `0x1800df3ed`
- name: `?UtilDuplicateSid@CommonUtil@@YAJPEAPEAXPEAX@Z`
- size: `133`
- prototype: `int(CommonUtil *__hidden this, void **, void *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800dec18`
- `0x1800df240`
- `0x1800dfa1c`

## callees

- `0x180004bd0`
- `0x1800df368`
- `0x1800dfc88`
- `0x1800e1690`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800df3bd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800df3bd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800df37a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800df37a`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilDuplicateSid(CommonUtil *this, void **a2, void *a3)
{
  DWORD LengthSid; // eax
  DWORD v6; // ebp
  unsigned __int64 v7; // r8
  int v8; // ebx
  void *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int LastFailure; // edi
  void *Block; // [rsp+60h] [rbp+18h] BYREF

  LengthSid = GetLengthSid(a2);
  Block = 0;
  v6 = LengthSid;
  v8 = CommonUtil::MpNewAlloc((CommonUtil *)&Block, (void **)LengthSid, v7);
  if ( v8 >= 0 )
  {
    v10 = Block;
    if ( CopySid(v6, Block, a2) )
    {
      *(_QWORD *)this = v10;
      return 0;
    }
    else
    {
      LastFailure = HrGetLastFailure(v12, v11);
      if ( v10 )
        operator delete(v10);
      return LastFailure;
    }
  }
  else
  {
    if ( Block )
      operator delete(Block);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x1800df368  push    rbx
0x1800df36a  push    rbp
0x1800df36b  push    rsi
0x1800df36c  push    rdi
0x1800df36d  sub     rsp, 28h
0x1800df371  mov     rdi, rcx
0x1800df374  mov     rsi, rdx
0x1800df377  mov     rcx, rdx; pSid
0x1800df37a  call    cs:__imp_GetLengthSid
0x1800df380  lea     rcx, [rsp+48h+Block]; this
0x1800df385  mov     [rsp+48h+Block], 0
0x1800df38e  mov     edx, eax; void **
0x1800df390  mov     ebp, eax
0x1800df392  call    ?MpNewAlloc@CommonUtil@@YAJPEAPEAX_K@Z; CommonUtil::MpNewAlloc(void * *,unsigned __int64)
0x1800df397  mov     ebx, eax
0x1800df399  test    eax, eax
0x1800df39b  jns     short loc_1800DF3B0
0x1800df39d  mov     rcx, [rsp+48h+Block]; Block
0x1800df3a2  test    rcx, rcx
0x1800df3a5  jz      short loc_1800DF3AC
0x1800df3a7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800df3ac  mov     eax, ebx
0x1800df3ae  jmp     short loc_1800DF3E4
0x1800df3b0  mov     rbx, [rsp+48h+Block]
0x1800df3b5  mov     r8, rsi; pSourceSid
0x1800df3b8  mov     rdx, rbx; pDestinationSid
0x1800df3bb  mov     ecx, ebp; nDestinationSidLength
0x1800df3bd  call    cs:__imp_CopySid
0x1800df3c3  test    eax, eax
0x1800df3c5  jnz     short loc_1800DF3DF
0x1800df3c7  call    HrGetLastFailure
0x1800df3cc  mov     edi, eax
0x1800df3ce  test    rbx, rbx
0x1800df3d1  jz      short loc_1800DF3DB
0x1800df3d3  mov     rcx, rbx; Block
0x1800df3d6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800df3db  mov     eax, edi
0x1800df3dd  jmp     short loc_1800DF3E4
0x1800df3df  mov     [rdi], rbx
0x1800df3e2  xor     eax, eax
0x1800df3e4  add     rsp, 28h
0x1800df3e8  pop     rdi
0x1800df3e9  pop     rsi
0x1800df3ea  pop     rbp
0x1800df3eb  pop     rbx
0x1800df3ec  retn
```
