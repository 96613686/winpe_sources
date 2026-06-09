# PathName(CLexer *,_objectinfo *)

- ea: `0x180016630`
- end: `0x1800166ea`
- name: `?PathName@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(struct CLexer *this, struct _objectinfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800164f8`

## callees

- `0x180016234`
- `0x180016368`
- `0x180016630`
- `0x1800167fc`
- `0x18001d6c0`

## pseudocode

```c
int __fastcall PathName(struct CLexer *this, struct _objectinfo *a2)
{
  int result; // eax
  unsigned __int16 *v5; // r8
  unsigned int v6; // [rsp+20h] [rbp-448h] BYREF
  unsigned int v7[3]; // [rsp+24h] [rbp-444h] BYREF
  unsigned __int16 v8[264]; // [rsp+30h] [rbp-438h] BYREF
  unsigned __int16 v9[264]; // [rsp+240h] [rbp-228h] BYREF

  v6 = 0;
  while ( 1 )
  {
    v7[0] = 0;
    result = CLexer::GetNextToken(this, v8, v7);
    if ( result < 0 )
      break;
    if ( v7[0] != 1 )
      return -2147463168;
    result = AddComponent(a2, v8, v5);
    if ( result < 0 )
      return result;
    result = CLexer::GetNextToken(this, v9, &v6);
    if ( result < 0 )
      return result;
    if ( v6 != 3 && v6 != 14 )
      return CLexer::PushBackToken(this);
  }
  return result;
}

```

## disassembly

```asm
0x180016630  mov     [rsp+arg_10], rbx
0x180016635  push    rdi
0x180016636  sub     rsp, 460h
0x18001663d  mov     rax, cs:__security_cookie
0x180016644  xor     rax, rsp
0x180016647  mov     [rsp+468h+var_18], rax
0x18001664f  mov     rdi, rdx
0x180016652  mov     [rsp+468h+var_448], 0
0x18001665a  mov     rbx, rcx
0x18001665d  lea     r8, [rsp+468h+var_444]; unsigned int *
0x180016662  mov     [rsp+468h+var_444], 0
0x18001666a  lea     rdx, [rsp+468h+var_438]; unsigned __int16 *
0x18001666f  mov     rcx, rbx; this
0x180016672  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x180016677  test    eax, eax
0x180016679  js      short loc_1800166C2
0x18001667b  cmp     [rsp+468h+var_444], 1
0x180016680  jnz     short loc_1800166E3
0x180016682  lea     rdx, [rsp+468h+var_438]; unsigned __int16 *
0x180016687  mov     rcx, rdi; struct _objectinfo *
0x18001668a  call    ?AddComponent@@YAJPEAU_objectinfo@@PEAG1@Z; AddComponent(_objectinfo *,ushort *,ushort *)
0x18001668f  test    eax, eax
0x180016691  js      short loc_1800166C2
0x180016693  lea     r8, [rsp+468h+var_448]; unsigned int *
0x180016698  mov     rcx, rbx; this
0x18001669b  lea     rdx, [rsp+468h+var_228]; unsigned __int16 *
0x1800166a3  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x1800166a8  test    eax, eax
0x1800166aa  js      short loc_1800166C2
0x1800166ac  cmp     [rsp+468h+var_448], 3
0x1800166b1  jz      short loc_18001665D
0x1800166b3  cmp     [rsp+468h+var_448], 0Eh
0x1800166b8  jz      short loc_18001665D
0x1800166ba  mov     rcx, rbx; this
0x1800166bd  call    ?PushBackToken@CLexer@@QEAAJXZ; CLexer::PushBackToken(void)
0x1800166c2  mov     rcx, [rsp+468h+var_18]
0x1800166ca  xor     rcx, rsp; StackCookie
0x1800166cd  call    __security_check_cookie
0x1800166d2  mov     rbx, [rsp+468h+arg_10]
0x1800166da  add     rsp, 460h
0x1800166e1  pop     rdi
0x1800166e2  retn
0x1800166e3  mov     eax, 80005000h
0x1800166e8  jmp     short loc_1800166C2
```
