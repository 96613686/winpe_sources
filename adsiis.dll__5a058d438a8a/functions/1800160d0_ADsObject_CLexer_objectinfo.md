# ADsObject(CLexer *,_objectinfo *)

- ea: `0x1800160d0`
- end: `0x18001622e`
- name: `?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(struct CLexer *, struct _objectinfo *)`
- caller_count: `10`
- callee_count: `7`
- tags: ``

## callers

- `0x180002c80`
- `0x180003bb8`
- `0x18000474c`
- `0x180009a44`
- `0x180009d90`
- `0x18000d638`
- `0x180012e6c`
- `0x180014fa4`
- `0x1800151fc`
- `0x180015664`

## callees

- `0x1800160d0`
- `0x180016368`
- `0x1800164f8`
- `0x1800166f0`
- `0x1800167fc`
- `0x180016818`
- `0x18001d6c0`

## pseudocode

```c
__int64 __fastcall ADsObject(struct CLexer *a1, struct _objectinfo *a2)
{
  __int64 result; // rax
  struct CLexer *v5; // rcx
  unsigned int v6[4]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 v7[264]; // [rsp+30h] [rbp-D0h] BYREF

  v6[0] = 0;
  result = ProviderName(a1, a2);
  if ( (int)result >= 0 )
  {
    *((_DWORD *)a2 + 135) = 28;
    *((_QWORD *)a2 + 69) = 0;
    result = CLexer::GetNextToken(a1, v7, v6);
    if ( (int)result >= 0 )
    {
      if ( v6[0] == 2 )
      {
        result = Type(a1, a2);
        if ( (int)result >= 0 )
        {
          result = CLexer::GetNextToken(a1, v7, v6);
          if ( (int)result >= 0 )
            return v6[0] != 4 ? 0x80005000 : 0;
        }
      }
      else
      {
        if ( v6[0] == 4 )
          return 0;
        CLexer::PushBackToken(a1);
        result = IISObject(v5, a2);
        if ( (int)result >= 0 )
        {
          result = CLexer::GetNextToken(a1, v7, v6);
          if ( (int)result >= 0 )
          {
            if ( v6[0] != 2 )
            {
              if ( v6[0] != 4 )
                return 2147500037LL;
              return 0;
            }
            result = Type(a1, a2);
            if ( (int)result >= 0 )
            {
              result = CLexer::GetNextToken(a1, v7, v6);
              if ( (int)result >= 0 )
              {
                if ( v6[0] != 4 )
                  return 2147504128LL;
                return 0;
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800160d0  mov     [rsp-8+arg_10], rbx
0x1800160d5  mov     [rsp-8+arg_18], rdi
0x1800160da  push    rbp
0x1800160db  lea     rbp, [rsp-150h]
0x1800160e3  sub     rsp, 250h
0x1800160ea  mov     rax, cs:__security_cookie
0x1800160f1  xor     rax, rsp
0x1800160f4  mov     [rbp+150h+var_10], rax
0x1800160fb  mov     rdi, rdx
0x1800160fe  mov     [rsp+250h+var_230], 0
0x180016106  mov     rbx, rcx
0x180016109  call    ?ProviderName@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ProviderName(CLexer *,_objectinfo *)
0x18001610e  test    eax, eax
0x180016110  js      loc_18001620A
0x180016116  lea     r8, [rsp+250h+var_230]; unsigned int *
0x18001611b  mov     dword ptr [rdi+21Ch], 1Ch
0x180016125  lea     rdx, [rsp+250h+var_220]; unsigned __int16 *
0x18001612a  mov     qword ptr [rdi+228h], 0
0x180016135  mov     rcx, rbx; this
0x180016138  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x18001613d  test    eax, eax
0x18001613f  js      loc_18001620A
0x180016145  cmp     [rsp+250h+var_230], 2
0x18001614a  jz      loc_1800161D5
0x180016150  cmp     [rsp+250h+var_230], 4
0x180016155  jz      short loc_1800161D1
0x180016157  mov     rcx, rbx; this
0x18001615a  call    ?PushBackToken@CLexer@@QEAAJXZ; CLexer::PushBackToken(void)
0x18001615f  mov     rdx, rdi; struct _objectinfo *
0x180016162  call    ?IISObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; IISObject(CLexer *,_objectinfo *)
0x180016167  test    eax, eax
0x180016169  js      loc_18001620A
0x18001616f  lea     r8, [rsp+250h+var_230]; unsigned int *
0x180016174  mov     rcx, rbx; this
0x180016177  lea     rdx, [rsp+250h+var_220]; unsigned __int16 *
0x18001617c  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x180016181  test    eax, eax
0x180016183  js      loc_18001620A
0x180016189  cmp     [rsp+250h+var_230], 2
0x18001618e  jz      short loc_18001619E
0x180016190  cmp     [rsp+250h+var_230], 4
0x180016195  jz      short loc_1800161D1
0x180016197  mov     eax, 80004005h
0x18001619c  jmp     short loc_18001620A
0x18001619e  mov     rdx, rdi; struct _objectinfo *
0x1800161a1  mov     rcx, rbx; struct CLexer *
0x1800161a4  call    ?Type@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; Type(CLexer *,_objectinfo *)
0x1800161a9  test    eax, eax
0x1800161ab  js      short loc_18001620A
0x1800161ad  lea     r8, [rsp+250h+var_230]; unsigned int *
0x1800161b2  mov     rcx, rbx; this
0x1800161b5  lea     rdx, [rsp+250h+var_220]; unsigned __int16 *
0x1800161ba  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x1800161bf  test    eax, eax
0x1800161c1  js      short loc_18001620A
0x1800161c3  cmp     [rsp+250h+var_230], 4
0x1800161c8  jz      short loc_1800161D1
0x1800161ca  mov     eax, 80005000h
0x1800161cf  jmp     short loc_18001620A
0x1800161d1  xor     eax, eax
0x1800161d3  jmp     short loc_18001620A
0x1800161d5  mov     rdx, rdi; struct _objectinfo *
0x1800161d8  mov     rcx, rbx; struct CLexer *
0x1800161db  call    ?Type@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; Type(CLexer *,_objectinfo *)
0x1800161e0  test    eax, eax
0x1800161e2  js      short loc_18001620A
0x1800161e4  lea     r8, [rsp+250h+var_230]; unsigned int *
0x1800161e9  mov     rcx, rbx; this
0x1800161ec  lea     rdx, [rsp+250h+var_220]; unsigned __int16 *
0x1800161f1  call    ?GetNextToken@CLexer@@QEAAJPEAGPEAK@Z; CLexer::GetNextToken(ushort *,ulong *)
0x1800161f6  test    eax, eax
0x1800161f8  js      short loc_18001620A
0x1800161fa  mov     eax, [rsp+250h+var_230]
0x1800161fe  sub     eax, 4
0x180016201  neg     eax
0x180016203  sbb     eax, eax
0x180016205  and     eax, 80005000h
0x18001620a  mov     rcx, [rbp+150h+var_10]
0x180016211  xor     rcx, rsp; StackCookie
0x180016214  call    __security_check_cookie
0x180016219  lea     r11, [rsp+250h+var_s0]
0x180016221  mov     rbx, [r11+20h]
0x180016225  mov     rdi, [r11+28h]
0x180016229  mov     rsp, r11
0x18001622c  pop     rbp
0x18001622d  retn
```
