# CommonUtil::UtilDuplicateSid(void * *,void *)

- ea: `0x1400106fc`
- end: `0x1400107a9`
- name: `?UtilDuplicateSid@CommonUtil@@YAJPEAPEAXPEAX@Z`
- size: `173`
- prototype: `int(CommonUtil *__hidden this, void **, void *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14000ff60`
- `0x140010598`
- `0x140010b34`

## callees

- `0x1400106fc`
- `0x140015574`
- `0x140017738`
- `0x14003a5c0`
- `0x14003aa90`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x140010720`
- `ADVAPI32!GetLengthSid` at `0x140010720`
- `ADVAPI32!CopySid` at `0x140010768`
- `ADVAPI32!CopySid` at `0x140010768`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilDuplicateSid(CommonUtil *this, void **a2, void *a3)
{
  void **LengthSid; // rbp
  unsigned __int64 v6; // r8
  int v7; // ebx
  void *v9; // rbx
  unsigned int LastFailure; // edi
  void *Block; // [rsp+20h] [rbp-28h] BYREF

  Block = 0;
  LengthSid = (void **)GetLengthSid(a2);
  v7 = CommonUtil::MpNewAlloc((CommonUtil *)&Block, LengthSid, v6);
  if ( v7 >= 0 )
  {
    v9 = Block;
    if ( CopySid((DWORD)LengthSid, Block, a2) )
    {
      *(_QWORD *)this = v9;
      return 0;
    }
    else
    {
      LastFailure = HrGetLastFailure();
      if ( v9 )
        operator delete(v9);
      return LastFailure;
    }
  }
  else
  {
    if ( Block )
      operator delete(Block);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x1400106fc  mov     [rsp+arg_10], rbx
0x140010701  push    rbp
0x140010702  push    rsi
0x140010703  push    rdi
0x140010704  sub     rsp, 30h
0x140010708  mov     rax, cs:__security_cookie
0x14001070f  xor     rax, rsp
0x140010712  mov     [rsp+48h+var_20], rax
0x140010717  mov     rdi, rcx
0x14001071a  mov     rsi, rdx
0x14001071d  mov     rcx, rdx; pSid
0x140010720  call    cs:__imp_GetLengthSid
0x140010726  lea     rcx, [rsp+48h+Block]; this
0x14001072b  mov     [rsp+48h+Block], 0
0x140010734  mov     edx, eax; void **
0x140010736  mov     ebp, eax
0x140010738  call    ?MpNewAlloc@CommonUtil@@YAJPEAPEAX_K@Z; CommonUtil::MpNewAlloc(void * *,unsigned __int64)
0x14001073d  mov     edx, eax
0x14001073f  mov     ebx, eax
0x140010741  shr     edx, 1Fh
0x140010744  test    dl, dl
0x140010746  jz      short loc_14001075B
0x140010748  mov     rcx, [rsp+48h+Block]; Block
0x14001074d  test    rcx, rcx
0x140010750  jz      short loc_140010757
0x140010752  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140010757  mov     eax, ebx
0x140010759  jmp     short loc_14001078F
0x14001075b  mov     rbx, [rsp+48h+Block]
0x140010760  mov     r8, rsi; pSourceSid
0x140010763  mov     rdx, rbx; pDestinationSid
0x140010766  mov     ecx, ebp; nDestinationSidLength
0x140010768  call    cs:__imp_CopySid
0x14001076e  test    eax, eax
0x140010770  jnz     short loc_14001078A
0x140010772  call    HrGetLastFailure
0x140010777  mov     edi, eax
0x140010779  test    rbx, rbx
0x14001077c  jz      short loc_140010786
0x14001077e  mov     rcx, rbx; Block
0x140010781  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140010786  mov     eax, edi
0x140010788  jmp     short loc_14001078F
0x14001078a  mov     [rdi], rbx
0x14001078d  xor     eax, eax
0x14001078f  mov     rcx, [rsp+48h+var_20]
0x140010794  xor     rcx, rsp; StackCookie
0x140010797  call    __security_check_cookie
0x14001079c  mov     rbx, [rsp+48h+arg_10]
0x1400107a1  add     rsp, 30h
0x1400107a5  pop     rdi
0x1400107a6  pop     rsi
0x1400107a7  pop     rbp
0x1400107a8  retn
```
