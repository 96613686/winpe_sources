# CreatePolicySecurityDescriptor(_POLICY *,_SECURITY_DESCRIPTOR_RELATIVE *,ulong)

- ea: `0x140005194`
- end: `0x14000545b`
- name: `?CreatePolicySecurityDescriptor@@YAKPEAU_POLICY@@PEAU_SECURITY_DESCRIPTOR_RELATIVE@@K@Z`
- size: `711`
- prototype: `__int64 __fastcall(struct _POLICY *, struct _SECURITY_DESCRIPTOR_RELATIVE *, __int16)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400064f8`

## callees

- `0x14000104c`
- `0x1400013b8`
- `0x140005194`
- `0x140008d30`
- `0x140008ef4`
- `0x140013ab7`

## import_xrefs

- `msvcrt!qsort` at `0x1400052ae`
- `msvcrt!qsort` at `0x1400052c7`
- `msvcrt!qsort` at `0x1400052ae`
- `msvcrt!qsort` at `0x1400052c7`
- `ntdll!EtwEventWrite` at `0x1400051fa`
- `ntdll!EtwEventWrite` at `0x140005304`
- `ntdll!EtwEventWrite` at `0x1400051fa`
- `ntdll!EtwEventWrite` at `0x140005304`

## pseudocode

```c
__int64 __fastcall CreatePolicySecurityDescriptor(
        struct _POLICY *a1,
        struct _SECURITY_DESCRIPTOR_RELATIVE *a2,
        __int16 a3)
{
  _QWORD *v5; // r15
  __int64 v7; // rbx
  __int64 v8; // r13
  __int64 v9; // r9
  void **i; // r12
  _QWORD *v11; // rdx
  _BYTE *v12; // rax
  int v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // r9
  struct _SECURITY_DESCRIPTOR_RELATIVE *v17; // rdi
  __int64 v18; // rbx
  unsigned __int16 *v19; // rdx
  __int64 v20; // [rsp+60h] [rbp-10h] BYREF

  v5 = (_QWORD *)AiAlloc(40LL * *((unsigned int *)a1 + 9));
  if ( !v5 )
    return 14;
  v7 = 0;
  v8 = 0;
  EtwEventWrite(EventHandle, SrpPolicyRuleSortStart, 0, 0);
  v9 = 0;
  for ( i = (void **)((char *)a1 + 40); (unsigned int)v9 < *((_DWORD *)a1 + 9); v9 = (unsigned int)(v9 + 1) )
  {
    v11 = *i;
    v12 = (_BYTE *)*((_QWORD *)*i + 5 * v9 + 3);
    if ( *v12 <= 0xCu && (v13 = 5186, _bittest(&v13, (unsigned __int8)*v12)) )
    {
      v14 = 5 * v7;
      v7 = (unsigned int)(v7 + 1);
      *(_OWORD *)&v11[v14] = *(_OWORD *)&v11[5 * v9];
      *(_OWORD *)&v11[v14 + 2] = *(_OWORD *)&v11[5 * v9 + 2];
      v11[v14 + 4] = v11[5 * v9 + 4];
    }
    else
    {
      v15 = 5 * v8;
      v8 = (unsigned int)(v8 + 1);
      *(_OWORD *)&v5[v15] = *(_OWORD *)&v11[5 * v9];
      *(_OWORD *)&v5[v15 + 2] = *(_OWORD *)&v11[5 * v9 + 2];
      v5[v15 + 4] = v11[5 * v9 + 4];
    }
  }
  qsort(*i, (unsigned int)v7, 0x28u, (_CoreCrtNonSecureSearchSortCompareFunction)ComparePolicyRule);
  qsort(v5, (unsigned int)v8, 0x28u, (_CoreCrtNonSecureSearchSortCompareFunction)ComparePolicyRule);
  memcpy_0((char *)*i + 40 * v7, v5, 40 * v8);
  EtwEventWrite(EventHandle, SrpPolicyRuleSortEnd, 0, 0);
  if ( (unsigned int)dword_140020000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140020000) )
  {
    v20 = *(_QWORD *)a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_140020000,
      (__int64)byte_14001A665,
      (__int64)&ActivityId,
      v16,
      &v20);
  }
  v17 = a2 + 2;
  *(_OWORD *)&a2->Revision = 0;
  a2->Dacl = 0;
  v18 = 0;
  a2->Revision = 1;
  a2->Control = -32764;
  a2->Owner = 20;
  *(_QWORD *)&a2[1].Revision = 0x500000000000101LL;
  a2[1].Group = 18;
  LOBYTE(a2[1].Sacl) = 2;
  HIWORD(a2[1].Sacl) = (a3 - 32) & 0xFFFC;
  LOWORD(a2[1].Dacl) = *((_WORD *)a1 + 18);
  HIWORD(a2[1].Dacl) = 0;
  for ( BYTE1(a2[1].Sacl) = 0;
        (unsigned int)v18 < *((_DWORD *)a1 + 9);
        v17 = (struct _SECURITY_DESCRIPTOR_RELATIVE *)((char *)v17 + v17->Control) )
  {
    v19 = (unsigned __int16 *)*((_QWORD *)*i + 5 * v18 + 3);
    memcpy_0(v17, v19, v19[1]);
    v18 = (unsigned int)(v18 + 1);
  }
  a2->Dacl = a2->Owner + 12;
  AiFree(v5);
  return 0;
}

```

## disassembly

```asm
0x140005194  mov     [rsp-38h+arg_8], rbx
0x140005199  mov     [rsp-38h+arg_10], r8d
0x14000519e  push    rbp
0x14000519f  push    rsi
0x1400051a0  push    rdi
0x1400051a1  push    r12
0x1400051a3  push    r13
0x1400051a5  push    r14
0x1400051a7  push    r15
0x1400051a9  mov     rbp, rsp
0x1400051ac  sub     rsp, 70h
0x1400051b0  mov     eax, [rcx+24h]
0x1400051b3  mov     r14, rcx
0x1400051b6  mov     rsi, rdx
0x1400051b9  lea     rcx, [rax+rax*4]
0x1400051bd  shl     rcx, 3
0x1400051c1  call    AiAlloc
0x1400051c6  mov     r15, rax
0x1400051c9  test    rax, rax
0x1400051cc  jnz     short loc_1400051D7
0x1400051ce  lea     eax, [r15+0Eh]
0x1400051d2  jmp     loc_140005443
0x1400051d7  mov     rcx, cs:?EventHandle@@3_KA; unsigned __int64 EventHandle
0x1400051de  lea     rdx, SrpPolicyRuleSortStart
0x1400051e5  xor     ebx, ebx
0x1400051e7  mov     [rbp+var_14], 0
0x1400051ee  xor     r9d, r9d
0x1400051f1  mov     [rbp+arg_0], ebx
0x1400051f4  xor     r8d, r8d
0x1400051f7  xor     r13d, r13d
0x1400051fa  call    cs:__imp_EtwEventWrite
0x140005200  xor     r9d, r9d
0x140005203  lea     r12, [r14+28h]
0x140005207  cmp     [r14+24h], ebx
0x14000520b  jbe     loc_14000529B
0x140005211  mov     rdx, [r12]
0x140005215  lea     r8, [r9+r9*4]
0x140005219  mov     rax, [rdx+r8*8+18h]
0x14000521e  cmp     byte ptr [rax], 0Ch
0x140005221  ja      short loc_140005259
0x140005223  movzx   eax, byte ptr [rax]
0x140005226  mov     ecx, 1442h
0x14000522b  bt      ecx, eax
0x14000522e  jnb     short loc_140005259
0x140005230  movups  xmm0, xmmword ptr [rdx+r8*8]
0x140005235  lea     rcx, [rbx+rbx*4]
0x140005239  inc     ebx
0x14000523b  movups  xmmword ptr [rdx+rcx*8], xmm0
0x14000523f  movups  xmm1, xmmword ptr [rdx+r8*8+10h]
0x140005245  movups  xmmword ptr [rdx+rcx*8+10h], xmm1
0x14000524a  movsd   xmm0, qword ptr [rdx+r8*8+20h]
0x140005251  movsd   qword ptr [rdx+rcx*8+20h], xmm0
0x140005257  jmp     short loc_14000528B
0x140005259  movups  xmm0, xmmword ptr [rdx+r8*8]
0x14000525e  lea     rcx, ds:0[r13*4]
0x140005266  add     rcx, r13
0x140005269  inc     r13d
0x14000526c  movups  xmmword ptr [r15+rcx*8], xmm0
0x140005271  movups  xmm1, xmmword ptr [rdx+r8*8+10h]
0x140005277  movups  xmmword ptr [r15+rcx*8+10h], xmm1
0x14000527d  movsd   xmm0, qword ptr [rdx+r8*8+20h]
0x140005284  movsd   qword ptr [r15+rcx*8+20h], xmm0
0x14000528b  inc     r9d
0x14000528e  cmp     r9d, [r14+24h]
0x140005292  jb      loc_140005211
0x140005298  mov     [rbp+arg_0], ebx
0x14000529b  mov     rcx, [r12]; Base
0x14000529f  lea     r9, ?ComparePolicyRule@@YAHPEBX0@Z; CompareFunction
0x1400052a6  mov     r8d, 28h ; '('; SizeOfElements
0x1400052ac  mov     edx, ebx; NumOfElements
0x1400052ae  call    cs:__imp_qsort
0x1400052b4  lea     r9, ?ComparePolicyRule@@YAHPEBX0@Z; CompareFunction
0x1400052bb  mov     edx, r13d; NumOfElements
0x1400052be  mov     r8d, 28h ; '('; SizeOfElements
0x1400052c4  mov     rcx, r15; Base
0x1400052c7  call    cs:__imp_qsort
0x1400052cd  mov     rax, [r12]
0x1400052d1  lea     r8, ds:0[r13*4]
0x1400052d9  add     r8, r13
0x1400052dc  lea     rcx, [rbx+rbx*4]
0x1400052e0  shl     r8, 3; Size
0x1400052e4  mov     rdx, r15; Src
0x1400052e7  lea     rcx, [rax+rcx*8]; void *
0x1400052eb  call    memcpy_0
0x1400052f0  mov     rcx, cs:?EventHandle@@3_KA; unsigned __int64 EventHandle
0x1400052f7  lea     rdx, SrpPolicyRuleSortEnd
0x1400052fe  xor     r9d, r9d
0x140005301  xor     r8d, r8d
0x140005304  call    cs:__imp_EtwEventWrite
0x14000530a  mov     eax, cs:dword_140020000
0x140005310  cmp     eax, 4
0x140005313  jbe     loc_14000539F
0x140005319  lea     rcx, dword_140020000
0x140005320  call    _tlgKeywordOn
0x140005325  test    al, al
0x140005327  jz      short loc_14000539F
0x140005329  mov     eax, [rbp+arg_0]
0x14000532c  lea     r8, ActivityId
0x140005333  mov     [rbp+arg_0], eax
0x140005336  lea     rdx, byte_14001A665
0x14000533d  mov     eax, [r14+24h]
0x140005341  lea     rcx, dword_140020000
0x140005348  mov     [rbp+var_20], eax
0x14000534b  mov     eax, [r14+0Ch]
0x14000534f  mov     [rbp+var_1C], eax
0x140005352  mov     eax, [r14+8]
0x140005356  mov     [rbp+var_18], eax
0x140005359  mov     rax, [r14]
0x14000535c  mov     [rbp+var_10], rax
0x140005360  lea     rax, [rbp+arg_0]
0x140005364  mov     [rsp+70h+var_28], rax
0x140005369  lea     rax, [rbp+arg_18]
0x14000536d  mov     [rsp+70h+var_30], rax
0x140005372  lea     rax, [rbp+var_20]
0x140005376  mov     [rsp+70h+var_38], rax
0x14000537b  lea     rax, [rbp+var_1C]
0x14000537f  mov     [rsp+70h+var_40], rax
0x140005384  lea     rax, [rbp+var_18]
0x140005388  mov     [rsp+70h+var_48], rax
0x14000538d  lea     rax, [rbp+var_10]
0x140005391  mov     [rsp+70h+var_50], rax
0x140005396  mov     [rbp+arg_18], r13d
0x14000539a  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000539f  xor     eax, eax
0x1400053a1  lea     rdi, [rsi+28h]
0x1400053a5  xorps   xmm0, xmm0
0x1400053a8  mov     ecx, 0FFFCh
0x1400053ad  movups  xmmword ptr [rsi], xmm0
0x1400053b0  mov     [rsi+10h], eax
0x1400053b3  xor     ebx, ebx
0x1400053b5  mov     byte ptr [rsi], 1
0x1400053b8  mov     word ptr [rsi+2], 8004h
0x1400053be  mov     dword ptr [rsi+4], 14h
0x1400053c5  movsd   xmm0, cs:qword_140018718
0x1400053cd  movsd   qword ptr [rsi+14h], xmm0
0x1400053d2  mov     eax, cs:dword_140018720
0x1400053d8  mov     [rsi+1Ch], eax
0x1400053db  mov     eax, [rbp+arg_10]
0x1400053de  sub     ax, 20h ; ' '
0x1400053e2  mov     byte ptr [rsi+20h], 2
0x1400053e6  and     ax, cx
0x1400053e9  mov     [rsi+22h], ax
0x1400053ed  movzx   eax, word ptr [r14+24h]
0x1400053f2  mov     [rsi+24h], ax
0x1400053f6  xor     eax, eax
0x1400053f8  mov     [rsi+26h], ax
0x1400053fc  mov     byte ptr [rsi+21h], 0
0x140005400  cmp     [r14+24h], eax
0x140005404  jbe     short loc_14000542F
0x140005406  mov     rax, [r12]
0x14000540a  lea     rcx, [rbx+rbx*4]
0x14000540e  mov     rdx, [rax+rcx*8+18h]; Src
0x140005413  mov     rcx, rdi; void *
0x140005416  movzx   r8d, word ptr [rdx+2]; Size
0x14000541b  call    memcpy_0
0x140005420  movzx   ecx, word ptr [rdi+2]
0x140005424  inc     ebx
0x140005426  add     rdi, rcx
0x140005429  cmp     ebx, [r14+24h]
0x14000542d  jb      short loc_140005406
0x14000542f  mov     ecx, [rsi+4]
0x140005432  add     ecx, 0Ch
0x140005435  mov     [rsi+10h], ecx
0x140005438  mov     rcx, r15
0x14000543b  call    AiFree
0x140005440  mov     eax, [rbp+var_14]
0x140005443  mov     rbx, [rsp+70h+arg_8]
0x14000544b  add     rsp, 70h
0x14000544f  pop     r15
0x140005451  pop     r14
0x140005453  pop     r13
0x140005455  pop     r12
0x140005457  pop     rdi
0x140005458  pop     rsi
0x140005459  pop     rbp
0x14000545a  retn
```
