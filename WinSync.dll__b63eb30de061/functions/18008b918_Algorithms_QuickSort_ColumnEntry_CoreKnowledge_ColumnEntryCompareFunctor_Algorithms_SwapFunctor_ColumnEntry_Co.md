# Algorithms::QuickSort<ColumnEntry,CoreKnowledge::ColumnEntryCompareFunctor,Algorithms::SwapFunctor<ColumnEntry>>(ColumnEntry *,ulong,CoreKnowledge::ColumnEntryCompareFunctor,Algorithms::SwapFunctor<ColumnEntry>)

- ea: `0x18008b918`
- end: `0x18008bc93`
- name: `??$QuickSort@UColumnEntry@@UColumnEntryCompareFunctor@CoreKnowledge@@U?$SwapFunctor@UColumnEntry@@@Algorithms@@@Algorithms@@SAXPEAUColumnEntry@@KUColumnEntryCompareFunctor@CoreKnowledge@@U?$SwapFunctor@UColumnEntry@@@0@@Z`
- size: `891`
- prototype: `__int64 __fastcall(struct SyncId *, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180007d6c`
- `0x18000ced0`
- `0x18008d6a0`

## callees

- `0x180008ab0`
- `0x18000c270`
- `0x180011f60`
- `0x18001a1f0`
- `0x18008b918`
- `0x18008bd3c`
- `0x18009323e`
- `0x180093270`

## pseudocode

```c
__int64 __fastcall Algorithms::QuickSort<ColumnEntry,CoreKnowledge::ColumnEntryCompareFunctor,Algorithms::SwapFunctor<ColumnEntry>>(
        struct SyncId *a1,
        unsigned int a2)
{
  __int64 v2; // rbx
  __int64 result; // rax
  int v5; // r12d
  char *v6; // r14
  unsigned __int64 v7; // rax
  char *v8; // r15
  _DWORD *v9; // rdi
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  struct SyncId *v13; // rdi
  struct SyncId *v14; // r13
  const struct SyncId *v15; // rbx
  int v16; // ebx
  struct SyncId *v17; // rax
  _BYTE v18[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  __int64 v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+30h] [rbp-D0h]
  _QWORD v22[62]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v23[62]; // [rsp+230h] [rbp+130h] BYREF

  v2 = a2;
  memset_0(v22, 0, sizeof(v22));
  result = (__int64)memset_0(v23, 0, sizeof(v23));
  if ( (unsigned int)v2 >= 2 )
  {
    v5 = 0;
    v6 = (char *)a1 + 24 * v2 - 24;
    while ( 1 )
    {
      while ( 1 )
      {
        v7 = -1431655765 * (unsigned int)((v6 - (char *)a1) >> 3) + 1;
        if ( (unsigned int)v7 <= 8 )
        {
          result = Algorithms::ShortSort<ColumnEntry,CoreKnowledge::ColumnEntryCompareFunctor,Algorithms::SwapFunctor<ColumnEntry>>(a1);
          goto LABEL_5;
        }
        v8 = (char *)a1 + 24 * (v7 >> 1);
        v9 = v8 + 16;
        if ( (int)SyncId::Compare(a1, (const struct SyncId *)v8) > 0 )
        {
          v19 = *((_DWORD *)a1 + 1);
          v20 = *((_QWORD *)a1 + 1);
          SyncId::AddRef((SyncId *)v18);
          v21 = *((_DWORD *)a1 + 4);
          v10 = v21;
          SyncId::operator=(a1, v8);
          *((_DWORD *)a1 + 4) = *v9;
          SyncId::operator=(v8, v18);
          *v9 = v10;
          SyncId::~SyncId((SyncId *)v18);
        }
        if ( (int)SyncId::Compare(a1, (const struct SyncId *)v6) > 0 )
        {
          v19 = *((_DWORD *)a1 + 1);
          v20 = *((_QWORD *)a1 + 1);
          SyncId::AddRef((SyncId *)v18);
          v21 = *((_DWORD *)a1 + 4);
          v11 = v21;
          SyncId::operator=(a1, v6);
          *((_DWORD *)a1 + 4) = *((_DWORD *)v6 + 4);
          SyncId::operator=(v6, v18);
          *((_DWORD *)v6 + 4) = v11;
          SyncId::~SyncId((SyncId *)v18);
        }
        if ( (int)SyncId::Compare((const struct SyncId *)v8, (const struct SyncId *)v6) > 0 )
        {
          v19 = *((_DWORD *)v8 + 1);
          v20 = *((_QWORD *)v8 + 1);
          SyncId::AddRef((SyncId *)v18);
          v21 = *v9;
          v12 = v21;
          SyncId::operator=(v8, v6);
          *v9 = *((_DWORD *)v6 + 4);
          SyncId::operator=(v6, v18);
          *((_DWORD *)v6 + 4) = v12;
          SyncId::~SyncId((SyncId *)v18);
        }
        v13 = a1;
        v14 = (struct SyncId *)v6;
        while ( 1 )
        {
          if ( v8 > (char *)v13 )
          {
            while ( 1 )
            {
              v13 = (struct SyncId *)((char *)v13 + 24);
              if ( v13 >= (struct SyncId *)v8 )
                break;
              if ( (int)SyncId::Compare(v13, (const struct SyncId *)v8) > 0 )
                goto LABEL_20;
            }
          }
          do
            v13 = (struct SyncId *)((char *)v13 + 24);
          while ( v13 <= (struct SyncId *)v6 && (int)SyncId::Compare(v13, (const struct SyncId *)v8) <= 0 );
          do
          {
LABEL_20:
            v15 = v14;
            v14 = (struct SyncId *)((char *)v14 - 24);
          }
          while ( v14 > (struct SyncId *)v8 && (int)SyncId::Compare(v14, (const struct SyncId *)v8) > 0 );
          if ( v14 < v13 )
            break;
          v19 = *((_DWORD *)v13 + 1);
          v20 = *((_QWORD *)v13 + 1);
          SyncId::AddRef((SyncId *)v18);
          v21 = *((_DWORD *)v13 + 4);
          v16 = v21;
          SyncId::operator=(v13, v14);
          *((_DWORD *)v13 + 4) = *((_DWORD *)v14 + 4);
          SyncId::operator=(v14, v18);
          *((_DWORD *)v14 + 4) = v16;
          SyncId::~SyncId((SyncId *)v18);
          v17 = v13;
          if ( v8 != (char *)v14 )
            v17 = (struct SyncId *)v8;
          v8 = (char *)v17;
        }
        if ( v8 < (char *)v15 )
        {
          while ( 1 )
          {
            v15 = (const struct SyncId *)((char *)v15 - 24);
            if ( v15 <= (const struct SyncId *)v8 )
              break;
            if ( (unsigned int)SyncId::Compare(v15, (const struct SyncId *)v8) )
              goto LABEL_32;
          }
        }
        do
          v15 = (const struct SyncId *)((char *)v15 - 24);
        while ( v15 > a1 && !(unsigned int)SyncId::Compare(v15, (const struct SyncId *)v8) );
LABEL_32:
        result = 0xAAAAAAAAAAAAAAABuLL * ((v15 - a1) >> 3);
        if ( result >= (__int64)(0xAAAAAAAAAAAAAAABuLL * ((v6 - (char *)v13) >> 3)) )
          break;
        if ( v13 < (struct SyncId *)v6 )
        {
          result = v5++;
          v22[result] = v13;
          v23[result] = v6;
        }
        if ( a1 >= v15 )
        {
LABEL_5:
          if ( --v5 < 0 )
            return result;
          a1 = (struct SyncId *)v22[v5];
          v6 = (char *)v23[v5];
        }
        else
        {
          v6 = (char *)v15;
        }
      }
      if ( a1 < v15 )
      {
        result = v5++;
        v22[result] = a1;
        v23[result] = v15;
      }
      if ( v13 >= (struct SyncId *)v6 )
        goto LABEL_5;
      a1 = v13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18008b918  mov     [rsp-8+arg_10], rbx
0x18008b91d  push    rbp
0x18008b91e  push    rsi
0x18008b91f  push    rdi
0x18008b920  push    r12
0x18008b922  push    r13
0x18008b924  push    r14
0x18008b926  push    r15
0x18008b928  lea     rbp, [rsp-330h]
0x18008b930  sub     rsp, 430h
0x18008b937  mov     rax, cs:__security_cookie
0x18008b93e  xor     rax, rsp
0x18008b941  mov     [rbp+360h+var_40], rax
0x18008b948  mov     ebx, edx
0x18008b94a  mov     rsi, rcx
0x18008b94d  mov     edi, 1F0h
0x18008b952  lea     rcx, [rsp+460h+var_420]; void *
0x18008b957  mov     r8d, edi; Size
0x18008b95a  xor     edx, edx; Val
0x18008b95c  call    memset_0
0x18008b961  mov     r8d, edi; Size
0x18008b964  lea     rcx, [rbp+360h+var_230]; void *
0x18008b96b  xor     edx, edx; Val
0x18008b96d  call    memset_0
0x18008b972  cmp     ebx, 2
0x18008b975  jb      loc_18008BC69
0x18008b97b  lea     r14, [rbx-1]
0x18008b97f  xor     r12d, r12d
0x18008b982  lea     r14, [r14+r14*2]
0x18008b986  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18008b990  lea     r14, [rsi+r14*8]
0x18008b994  mov     rax, r14
0x18008b997  mov     rcx, rsi; struct SyncId *
0x18008b99a  sub     rax, rsi
0x18008b99d  sar     rax, 3
0x18008b9a1  imul    rax, rdx
0x18008b9a5  inc     eax
0x18008b9a7  cmp     eax, 8
0x18008b9aa  ja      short loc_18008B9DA
0x18008b9ac  mov     rdx, r14
0x18008b9af  call    ??$ShortSort@UColumnEntry@@UColumnEntryCompareFunctor@CoreKnowledge@@U?$SwapFunctor@UColumnEntry@@@Algorithms@@@Algorithms@@CAXPEAUColumnEntry@@0UColumnEntryCompareFunctor@CoreKnowledge@@U?$SwapFunctor@UColumnEntry@@@0@@Z; Algorithms::ShortSort<ColumnEntry,CoreKnowledge::ColumnEntryCompareFunctor,Algorithms::SwapFunctor<ColumnEntry>>(ColumnEntry *,ColumnEntry *,CoreKnowledge::ColumnEntryCompareFunctor,Algorithms::SwapFunctor<ColumnEntry>)
0x18008b9b4  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18008b9be  sub     r12d, 1
0x18008b9c2  js      loc_18008BC69
0x18008b9c8  movsxd  rax, r12d
0x18008b9cb  mov     rsi, [rsp+rax*8+460h+var_420]
0x18008b9d0  mov     r14, [rbp+rax*8+360h+var_230]
0x18008b9d8  jmp     short loc_18008B994
0x18008b9da  shr     rax, 1
0x18008b9dd  lea     rax, [rax+rax*2]
0x18008b9e1  lea     r15, [rsi+rax*8]
0x18008b9e5  mov     rdx, r15; struct SyncId *
0x18008b9e8  lea     rdi, [r15+10h]
0x18008b9ec  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18008b9f1  test    eax, eax
0x18008b9f3  jle     short loc_18008BA3F
0x18008b9f5  mov     eax, [rsi+4]
0x18008b9f8  lea     rcx, [rsp+460h+var_440]; this
0x18008b9fd  mov     [rsp+460h+var_43C], eax
0x18008ba01  mov     rax, [rsi+8]
0x18008ba05  mov     [rsp+460h+var_438], rax
0x18008ba0a  call    ?AddRef@SyncId@@AEAAXXZ; SyncId::AddRef(void)
0x18008ba0f  mov     ebx, [rsi+10h]
0x18008ba12  mov     rdx, r15
0x18008ba15  mov     rcx, rsi
0x18008ba18  mov     [rsp+460h+var_430], ebx
0x18008ba1c  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18008ba21  mov     eax, [rdi]
0x18008ba23  lea     rdx, [rsp+460h+var_440]
0x18008ba28  mov     rcx, r15
0x18008ba2b  mov     [rsi+10h], eax
0x18008ba2e  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18008ba33  lea     rcx, [rsp+460h+var_440]; this
0x18008ba38  mov     [rdi], ebx
0x18008ba3a  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18008ba3f  mov     rdx, r14; struct SyncId *
0x18008ba42  mov     rcx, rsi; struct SyncId *
0x18008ba45  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18008ba4a  test    eax, eax
0x18008ba4c  jle     short loc_18008BA9C
0x18008ba4e  mov     eax, [rsi+4]
0x18008ba51  lea     rcx, [rsp+460h+var_440]; this
0x18008ba56  mov     [rsp+460h+var_43C], eax
0x18008ba5a  mov     rax, [rsi+8]
0x18008ba5e  mov     [rsp+460h+var_438], rax
0x18008ba63  call    ?AddRef@SyncId@@AEAAXXZ; SyncId::AddRef(void)
0x18008ba68  mov     ebx, [rsi+10h]
0x18008ba6b  mov     rdx, r14
0x18008ba6e  mov     rcx, rsi
0x18008ba71  mov     [rsp+460h+var_430], ebx
0x18008ba75  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18008ba7a  mov     eax, [r14+10h]
0x18008ba7e  lea     rdx, [rsp+460h+var_440]
0x18008ba83  mov     rcx, r14
0x18008ba86  mov     [rsi+10h], eax
0x18008ba89  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18008ba8e  lea     rcx, [rsp+460h+var_440]; this
0x18008ba93  mov     [r14+10h], ebx
0x18008ba97  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18008ba9c  mov     rdx, r14; struct SyncId *
0x18008ba9f  mov     rcx, r15; struct SyncId *
0x18008baa2  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18008baa7  test    eax, eax
0x18008baa9  jle     short loc_18008BAF8
0x18008baab  mov     eax, [r15+4]
0x18008baaf  lea     rcx, [rsp+460h+var_440]; this
0x18008bab4  mov     [rsp+460h+var_43C], eax
0x18008bab8  mov     rax, [r15+8]
0x18008babc  mov     [rsp+460h+var_438], rax
0x18008bac1  call    ?AddRef@SyncId@@AEAAXXZ; SyncId::AddRef(void)
0x18008bac6  mov     ebx, [rdi]
0x18008bac8  mov     rdx, r14
0x18008bacb  mov     rcx, r15
0x18008bace  mov     [rsp+460h+var_430], ebx
0x18008bad2  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18008bad7  mov     eax, [r14+10h]
0x18008badb  lea     rdx, [rsp+460h+var_440]
0x18008bae0  mov     rcx, r14
0x18008bae3  mov     [rdi], eax
0x18008bae5  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18008baea  lea     rcx, [rsp+460h+var_440]; this
0x18008baef  mov     [r14+10h], ebx
0x18008baf3  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18008baf8  mov     rdi, rsi
0x18008bafb  mov     r13, r14
0x18008bafe  cmp     r15, rdi
0x18008bb01  jbe     short loc_18008BB1D
0x18008bb03  add     rdi, 18h
0x18008bb07  cmp     rdi, r15
0x18008bb0a  jnb     short loc_18008BB1D
0x18008bb0c  mov     rdx, r15; struct SyncId *
0x18008bb0f  mov     rcx, rdi; struct SyncId *
0x18008bb12  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18008bb17  test    eax, eax
0x18008bb19  jle     short loc_18008BB03
0x18008bb1b  jmp     short loc_18008BB35
0x18008bb1d  add     rdi, 18h
0x18008bb21  cmp     rdi, r14
0x18008bb24  ja      short loc_18008BB35
0x18008bb26  mov     rdx, r15; struct SyncId *
0x18008bb29  mov     rcx, rdi; struct SyncId *
0x18008bb2c  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18008bb31  test    eax, eax
0x18008bb33  jle     short loc_18008BB1D
0x18008bb35  mov     rbx, r13
0x18008bb38  sub     r13, 18h
0x18008bb3c  cmp     r13, r15
0x18008bb3f  jbe     short loc_18008BB50
0x18008bb41  mov     rdx, r15; struct SyncId *
0x18008bb44  mov     rcx, r13; struct SyncId *
0x18008bb47  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18008bb4c  test    eax, eax
0x18008bb4e  jg      short loc_18008BB35
0x18008bb50  cmp     r13, rdi
0x18008bb53  jb      short loc_18008BBB5
0x18008bb55  mov     eax, [rdi+4]
0x18008bb58  lea     rcx, [rsp+460h+var_440]; this
0x18008bb5d  mov     [rsp+460h+var_43C], eax
0x18008bb61  mov     rax, [rdi+8]
0x18008bb65  mov     [rsp+460h+var_438], rax
0x18008bb6a  call    ?AddRef@SyncId@@AEAAXXZ; SyncId::AddRef(void)
0x18008bb6f  mov     ebx, [rdi+10h]
0x18008bb72  mov     rdx, r13
0x18008bb75  mov     rcx, rdi
0x18008bb78  mov     [rsp+460h+var_430], ebx
0x18008bb7c  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18008bb81  mov     eax, [r13+10h]
0x18008bb85  lea     rdx, [rsp+460h+var_440]
0x18008bb8a  mov     rcx, r13
0x18008bb8d  mov     [rdi+10h], eax
0x18008bb90  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18008bb95  lea     rcx, [rsp+460h+var_440]; this
0x18008bb9a  mov     [r13+10h], ebx
0x18008bb9e  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18008bba3  cmp     r15, r13
0x18008bba6  mov     rax, rdi
0x18008bba9  cmovnz  rax, r15
0x18008bbad  mov     r15, rax
0x18008bbb0  jmp     loc_18008BAFE
0x18008bbb5  cmp     r15, rbx
0x18008bbb8  jnb     short loc_18008BBD4
0x18008bbba  sub     rbx, 18h
0x18008bbbe  cmp     rbx, r15
0x18008bbc1  jbe     short loc_18008BBD4
0x18008bbc3  mov     rdx, r15; struct SyncId *
0x18008bbc6  mov     rcx, rbx; struct SyncId *
0x18008bbc9  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18008bbce  test    eax, eax
0x18008bbd0  jz      short loc_18008BBBA
0x18008bbd2  jmp     short loc_18008BBEC
0x18008bbd4  sub     rbx, 18h
0x18008bbd8  cmp     rbx, rsi
0x18008bbdb  jbe     short loc_18008BBEC
0x18008bbdd  mov     rdx, r15; struct SyncId *
0x18008bbe0  mov     rcx, rbx; struct SyncId *
0x18008bbe3  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x18008bbe8  test    eax, eax
0x18008bbea  jz      short loc_18008BBD4
0x18008bbec  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18008bbf6  mov     rcx, r14
0x18008bbf9  sub     rcx, rdi
0x18008bbfc  mov     rax, rbx
0x18008bbff  sub     rax, rsi
0x18008bc02  sar     rcx, 3
0x18008bc06  sar     rax, 3
0x18008bc0a  imul    rcx, rdx
0x18008bc0e  imul    rax, rdx
0x18008bc12  cmp     rax, rcx
0x18008bc15  jl      short loc_18008BC40
0x18008bc17  cmp     rsi, rbx
0x18008bc1a  jnb     short loc_18008BC2F
0x18008bc1c  movsxd  rax, r12d
0x18008bc1f  inc     r12d
0x18008bc22  mov     [rsp+rax*8+460h+var_420], rsi
0x18008bc27  mov     [rbp+rax*8+360h+var_230], rbx
0x18008bc2f  cmp     rdi, r14
0x18008bc32  jnb     loc_18008B9BE
0x18008bc38  mov     rsi, rdi
0x18008bc3b  jmp     loc_18008B994
0x18008bc40  cmp     rdi, r14
0x18008bc43  jnb     short loc_18008BC58
0x18008bc45  movsxd  rax, r12d
0x18008bc48  inc     r12d
0x18008bc4b  mov     [rsp+rax*8+460h+var_420], rdi
0x18008bc50  mov     [rbp+rax*8+360h+var_230], r14
0x18008bc58  cmp     rsi, rbx
0x18008bc5b  jnb     loc_18008B9BE
0x18008bc61  mov     r14, rbx
0x18008bc64  jmp     loc_18008B994
0x18008bc69  mov     rcx, [rbp+360h+var_40]
0x18008bc70  xor     rcx, rsp; StackCookie
0x18008bc73  call    __security_check_cookie
0x18008bc78  mov     rbx, [rsp+460h+arg_10]
0x18008bc80  add     rsp, 430h
0x18008bc87  pop     r15
0x18008bc89  pop     r14
0x18008bc8b  pop     r13
0x18008bc8d  pop     r12
0x18008bc8f  pop     rdi
0x18008bc90  pop     rsi
0x18008bc91  pop     rbp
0x18008bc92  retn
```
