# NormalizeSpaceFunctionExpression::Evaluate(XPathEvaluationContext *,String &)

- ea: `0x18000bc00`
- end: `0x18000bd90`
- name: `?Evaluate@NormalizeSpaceFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEAVString@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(NormalizeSpaceFunctionExpression *this, struct XPathEvaluationContext *, struct String *)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path`

## callees

- `0x1800052bc`
- `0x18000a640`
- `0x18000a690`
- `0x18000bc00`
- `0x18000e594`
- `0x180010ee0`
- `0x180010f08`
- `0x180010f98`
- `0x180011840`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall NormalizeSpaceFunctionExpression::Evaluate(
        NormalizeSpaceFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        struct String *a3)
{
  XPathNavigatorInternal *ContextNode; // rax
  __int64 result; // rax
  int v6; // ebx
  char v7; // r14
  __int64 v8; // rsi
  String *v9; // rcx
  unsigned int v10; // r9d
  const unsigned __int16 *v11; // rcx
  __int64 v12; // r8
  char v13; // dl
  unsigned __int16 *v14; // [rsp+20h] [rbp-30h] BYREF
  __int16 v15; // [rsp+28h] [rbp-28h] BYREF
  char v16; // [rsp+2Ah] [rbp-26h]
  int v17; // [rsp+2Ch] [rbp-24h]
  unsigned __int16 *Src; // [rsp+30h] [rbp-20h]
  unsigned __int64 v19; // [rsp+38h] [rbp-18h]

  if ( *((_DWORD *)this + 9) )
  {
    result = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *))(***((_QWORD ***)this + 3) + 64LL))(
               **((_QWORD **)this + 3),
               a2);
  }
  else
  {
    v14 = 0;
    ContextNode = XPathEvaluationContext::QueryContextNode(a2);
    result = XPathNavigatorInternal::GetValue(ContextNode, (const unsigned __int16 **)&v14);
    if ( (int)result < 0 )
      return result;
    result = String::Initialize(a3, v14);
  }
  v6 = result;
  if ( (int)result >= 0 )
  {
    v16 = 0;
    Src = (unsigned __int16 *)&v15;
    v17 = 2;
    v7 = 0;
    v15 = 0;
    v8 = 0;
    LODWORD(v19) = 0;
    while ( (unsigned int)v8 < String::QueryCCH(a3) )
    {
      v11 = &qword_180016F98;
      if ( *(_QWORD *)a3 )
        v11 = *(const unsigned __int16 **)a3;
      v12 = v11[v8];
      if ( (v12 & 0xFF00) != 0 )
        v13 = *((_BYTE *)(&g_apCharTables)[(unsigned __int64)v11[v8] >> 8] + (unsigned __int8)v11[v8]);
      else
        v13 = *((_BYTE *)&g_anCharProps + v12);
      if ( (v13 & 1) != 0 )
      {
        if ( !v7 )
        {
          STRU::Append((STRU *)&v15, L" ", 0, v10);
          if ( v6 < 0 )
            goto LABEL_21;
          v7 = 1;
        }
      }
      else
      {
        LODWORD(v14) = (unsigned __int16)v12;
        v7 = 0;
        v6 = STRU::Append((STRU *)&v15, (const unsigned __int16 *)&v14, 0, v10);
        if ( v6 < 0 )
          goto LABEL_21;
      }
      v8 = (unsigned int)(v8 + 1);
    }
    v6 = String::Initialize(v9, Src, (unsigned int)v19);
    if ( v6 >= 0 )
      v6 = 0;
LABEL_21:
    BUFFER::~BUFFER((BUFFER *)&v15);
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x18000bc00  mov     [rsp-28h+arg_18], rbx
0x18000bc05  push    rbp
0x18000bc06  push    rsi
0x18000bc07  push    rdi
0x18000bc08  push    r12
0x18000bc0a  push    r14
0x18000bc0c  mov     rbp, rsp
0x18000bc0f  sub     rsp, 50h
0x18000bc13  mov     rax, cs:__security_cookie
0x18000bc1a  xor     rax, rsp
0x18000bc1d  mov     [rbp+var_10], rax
0x18000bc21  cmp     dword ptr [rcx+24h], 0
0x18000bc25  mov     rdi, r8
0x18000bc28  jnz     loc_18000BCDC
0x18000bc2e  mov     rcx, rdx; this
0x18000bc31  mov     [rbp+var_30], 0
0x18000bc39  call    ?QueryContextNode@XPathEvaluationContext@@QEAAAEAVXPathNavigatorInternal@@XZ; XPathEvaluationContext::QueryContextNode(void)
0x18000bc3e  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x18000bc42  mov     rcx, rax; this
0x18000bc45  call    ?GetValue@XPathNavigatorInternal@@QEAAJPEAPEBG@Z; XPathNavigatorInternal::GetValue(ushort const * *)
0x18000bc4a  test    eax, eax
0x18000bc4c  js      loc_18000BD70
0x18000bc52  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x18000bc56  mov     rcx, rdi; this
0x18000bc59  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x18000bc5e  mov     ebx, eax
0x18000bc60  test    eax, eax
0x18000bc62  js      loc_18000BD70
0x18000bc68  lea     rax, [rbp+var_28]
0x18000bc6c  mov     [rbp+var_26], 0
0x18000bc70  mov     [rbp+Src], rax
0x18000bc74  lea     r12, cs:180000000h
0x18000bc7b  xor     eax, eax
0x18000bc7d  mov     [rbp+var_24], 2
0x18000bc84  xor     r14b, r14b
0x18000bc87  mov     [rbp+var_28], ax
0x18000bc8b  xor     esi, esi
0x18000bc8d  mov     dword ptr [rbp+var_18], 0
0x18000bc94  mov     rcx, rdi; this
0x18000bc97  call    ?QueryCCH@String@@QEBAKXZ; String::QueryCCH(void)
0x18000bc9c  cmp     esi, eax
0x18000bc9e  jnb     loc_18000BD50
0x18000bca4  cmp     qword ptr [rdi], 0
0x18000bca8  lea     rcx, qword_180016F98
0x18000bcaf  mov     eax, 0FF00h
0x18000bcb4  cmovnz  rcx, [rdi]
0x18000bcb8  movzx   r8d, word ptr [rcx+rsi*2]
0x18000bcbd  test    ax, r8w
0x18000bcc1  jz      short loc_18000BCF4
0x18000bcc3  mov     eax, r8d
0x18000bcc6  movzx   ecx, r8b
0x18000bcca  shr     rax, 8
0x18000bcce  mov     rax, ds:rva ?g_apCharTables@@3PAPEAEA[r12+rax*8]; uchar * near * g_apCharTables ...
0x18000bcd6  movzx   edx, byte ptr [rax+rcx]
0x18000bcda  jmp     short loc_18000BCFD
0x18000bcdc  mov     rax, [rcx+18h]
0x18000bce0  mov     rcx, [rax]
0x18000bce3  mov     rax, [rcx]
0x18000bce6  mov     rax, [rax+40h]
0x18000bcea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcef  jmp     loc_18000BC5E
0x18000bcf4  movzx   edx, byte ptr [r8+r12+24EA0h]
0x18000bcfd  and     edx, 1
0x18000bd00  test    edx, edx
0x18000bd02  jz      short loc_18000BD25
0x18000bd04  test    r14b, r14b
0x18000bd07  jnz     short loc_18000BD49
0x18000bd09  xor     r8d, r8d; unsigned int
0x18000bd0c  lea     rdx, asc_180017244; " "
0x18000bd13  lea     rcx, [rbp+var_28]; this
0x18000bd17  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x18000bd1c  test    ebx, ebx
0x18000bd1e  js      short loc_18000BD65
0x18000bd20  mov     r14b, 1
0x18000bd23  jmp     short loc_18000BD49
0x18000bd25  mov     word ptr [rbp+var_30], r8w
0x18000bd2a  lea     rdx, [rbp+var_30]; unsigned __int16 *
0x18000bd2e  xor     eax, eax
0x18000bd30  lea     rcx, [rbp+var_28]; this
0x18000bd34  xor     r8d, r8d; unsigned int
0x18000bd37  mov     word ptr [rbp+var_30+2], ax
0x18000bd3b  xor     r14b, r14b
0x18000bd3e  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x18000bd43  mov     ebx, eax
0x18000bd45  test    eax, eax
0x18000bd47  js      short loc_18000BD65
0x18000bd49  inc     esi
0x18000bd4b  jmp     loc_18000BC94
0x18000bd50  mov     r8d, dword ptr [rbp+var_18]; unsigned __int64
0x18000bd54  mov     rdx, [rbp+Src]; Src
0x18000bd58  call    ?Initialize@String@@QEAAJPEBG_K@Z; String::Initialize(ushort const *,unsigned __int64)
0x18000bd5d  mov     ebx, eax
0x18000bd5f  test    eax, eax
0x18000bd61  js      short loc_18000BD65
0x18000bd63  xor     ebx, ebx
0x18000bd65  lea     rcx, [rbp+var_28]; this
0x18000bd69  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000bd6e  mov     eax, ebx
0x18000bd70  mov     rcx, [rbp+var_10]
0x18000bd74  xor     rcx, rsp; StackCookie
0x18000bd77  call    __security_check_cookie
0x18000bd7c  mov     rbx, [rsp+50h+arg_18]
0x18000bd84  add     rsp, 50h
0x18000bd88  pop     r14
0x18000bd8a  pop     r12
0x18000bd8c  pop     rdi
0x18000bd8d  pop     rsi
0x18000bd8e  pop     rbp
0x18000bd8f  retn
```
