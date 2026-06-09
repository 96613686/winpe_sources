# CBinaryAutoList::_SaveColumnLists(IStream *)

- ea: `0x180044518`
- end: `0x1800448ac`
- name: `?_SaveColumnLists@CBinaryAutoList@@AEAAJPEAUIStream@@@Z`
- size: `916`
- prototype: `int(CBinaryAutoList *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180043cf0`

## callees

- `0x180042a50`
- `0x180042b90`
- `0x180044518`
- `0x1800448b4`
- `0x180044938`
- `0x180044a6c`
- `0x180044ae0`
- `0x18004a5c0`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IStream_Write` at `0x18004457b`
- `SHCORE!IStream_Write` at `0x18004468c`
- `SHCORE!IStream_Write` at `0x1800446b3`
- `SHCORE!IStream_Write` at `0x180044780`
- `SHCORE!IStream_Write` at `0x1800447c3`
- `SHCORE!IStream_Write` at `0x1800447fc`
- `SHCORE!IStream_Write` at `0x180044823`
- `SHCORE!IStream_Write` at `0x18004457b`
- `SHCORE!IStream_Write` at `0x18004468c`
- `SHCORE!IStream_Write` at `0x1800446b3`
- `SHCORE!IStream_Write` at `0x180044780`
- `SHCORE!IStream_Write` at `0x1800447c3`
- `SHCORE!IStream_Write` at `0x1800447fc`
- `SHCORE!IStream_Write` at `0x180044823`

## pseudocode

```c
__int64 __fastcall CBinaryAutoList::_SaveColumnLists(CBinaryAutoList *this, struct IStream *a2)
{
  HRESULT appended; // r14d
  struct _DSA *v5; // rbx
  struct _DSA *v6; // rsi
  unsigned int v7; // edi
  __int64 v8; // rcx
  __int64 v9; // rax
  ULONG v10; // ebx
  struct IUnknown *v11; // rcx
  PVOID v13; // rax
  HDSA v14; // rdi
  unsigned int v15; // r15d
  __int64 v16; // rcx
  PVOID ItemPtr; // rax
  PVOID v18; // rax
  struct _DSA *v19; // rbx
  __int64 v20; // rax
  ULONG v21; // r15d
  unsigned __int64 v22; // rbx
  HDSA hdsa; // [rsp+30h] [rbp-40h] BYREF
  BOOL pv; // [rsp+38h] [rbp-38h] BYREF
  struct IUnknown *v25; // [rsp+40h] [rbp-30h] BYREF
  __int128 pitem; // [rsp+48h] [rbp-28h] BYREF
  __int64 v27; // [rsp+58h] [rbp-18h] BYREF

  v25 = 0;
  pv = (*(int (__fastcall **)(_QWORD, GUID *, struct IUnknown **))(**((_QWORD **)this + 4) + 80LL))(
         *((_QWORD *)this + 4),
         &GUID_c92f9791_754f_4205_9d3d_3ec1e04b03f9,
         &v25) >= 0;
  appended = IStream_Write(a2, &pv, 4u);
  if ( appended >= 0 )
  {
    if ( !pv || (appended = IUnknown_SaveToStream(a2, 1, v25), appended >= 0) )
    {
      hdsa = g_pfn_DSA_Create(20, 8);
      v5 = hdsa;
      if ( hdsa )
      {
        v6 = 0;
        appended = 0;
        v7 = 0;
        while ( appended >= 0 )
        {
          v8 = *((_QWORD *)this + 4);
          LODWORD(v27) = 0;
          pitem = 0;
          if ( (*(int (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v8 + 40LL))(v8, v7, &pitem) < 0 )
          {
            v6 = v5;
            v5 = 0;
            break;
          }
          appended = CDSA_Base<_tagpropertykey>::AppendItem(&hdsa, &pitem);
          ++v7;
        }
        if ( v5 )
          DSA_Destroy(v5);
        if ( appended >= 0 )
        {
          if ( v6 )
            v9 = *(unsigned int *)v6;
          else
            v9 = 0;
          LODWORD(hdsa) = v9;
          v10 = 20 * v9;
          if ( (unsigned __int64)(20 * v9) <= 0xFFFFFFFF )
          {
            appended = IStream_Write(a2, &hdsa, 4u);
            if ( appended >= 0 )
            {
              if ( !(_DWORD)hdsa
                || (v13 = g_pfn_DSA_GetItemPtr(v6, 0), appended = IStream_Write(a2, v13, v10), appended >= 0) )
              {
                v14 = g_pfn_DSA_Create(24, 8);
                if ( v14 )
                {
                  appended = 0;
                  v15 = 0;
                  while ( appended >= 0 )
                  {
                    v16 = *((_QWORD *)this + 4);
                    v27 = 0;
                    pitem = 0;
                    if ( (*(int (__fastcall **)(__int64, _QWORD, __int128 *, char *))(*(_QWORD *)v16 + 56LL))(
                           v16,
                           v15,
                           &pitem,
                           (char *)&v27 + 4) < 0 )
                    {
                      LODWORD(hdsa) = *(_DWORD *)v14;
                      v22 = 24LL * (unsigned int)hdsa;
                      if ( v22 <= 0xFFFFFFFF )
                      {
                        appended = IStream_Write(a2, &hdsa, 4u);
                        if ( appended >= 0 )
                        {
                          if ( !(_DWORD)hdsa
                            || (v18 = g_pfn_DSA_GetItemPtr(v14, 0), appended = IStream_Write(a2, v18, v22),
                                                                    appended >= 0) )
                          {
                            hdsa = 0;
                            appended = CBinaryAutoList::_GetRelevanceList(this, &hdsa);
                            if ( appended >= 0 )
                            {
                              v19 = hdsa;
                              if ( hdsa )
                                v20 = *(unsigned int *)hdsa;
                              else
                                v20 = 0;
                              LODWORD(hdsa) = v20;
                              v21 = 20 * v20;
                              if ( (unsigned __int64)(20 * v20) <= 0xFFFFFFFF )
                              {
                                appended = IStream_Write(a2, &hdsa, 4u);
                                if ( appended >= 0 && (_DWORD)hdsa )
                                {
                                  ItemPtr = g_pfn_DSA_GetItemPtr(v19, 0);
                                  appended = IStream_Write(a2, ItemPtr, v21);
                                }
                              }
                              else
                              {
                                appended = -2147024362;
                              }
                              if ( v19 )
                                DSA_Destroy(v19);
                            }
                          }
                        }
                      }
                      else
                      {
                        appended = -2147024362;
                      }
                      break;
                    }
                    appended = 0;
                    if ( DSA_InsertItem(v14, 0x7FFFFFFF, &pitem) == -1 )
                      appended = -2147024882;
                    ++v15;
                  }
                  DSA_Destroy(v14);
                }
                else
                {
                  appended = -2147024882;
                }
              }
            }
          }
          else
          {
            appended = -2147024362;
          }
          if ( v6 )
            DSA_Destroy(v6);
        }
      }
      else
      {
        appended = -2147024882;
      }
    }
  }
  v11 = v25;
  v25 = 0;
  if ( v11 )
    ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180044518  mov     [rsp-38h+arg_10], rbx
0x18004451d  push    rbp
0x18004451e  push    rsi
0x18004451f  push    rdi
0x180044520  push    r12
0x180044522  push    r13
0x180044524  push    r14
0x180044526  push    r15
0x180044528  mov     rbp, rsp
0x18004452b  sub     rsp, 70h
0x18004452f  mov     rax, cs:__security_cookie
0x180044536  xor     rax, rsp
0x180044539  mov     [rbp+var_10], rax
0x18004453d  mov     r13, rcx
0x180044540  mov     [rbp+var_30], 0
0x180044548  mov     rcx, [rcx+20h]
0x18004454c  lea     r8, [rbp+var_30]
0x180044550  mov     r12, rdx
0x180044553  lea     rdx, _GUID_c92f9791_754f_4205_9d3d_3ec1e04b03f9
0x18004455a  mov     rax, [rcx]
0x18004455d  mov     rax, [rax+50h]
0x180044561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044566  not     eax
0x180044568  lea     rdx, [rbp+pv]; pv
0x18004456c  shr     eax, 1Fh
0x18004456f  mov     r8d, 4; cb
0x180044575  mov     rcx, r12; pstm
0x180044578  mov     [rbp+pv], eax
0x18004457b  call    cs:__imp_IStream_Write
0x180044581  mov     r14d, eax
0x180044584  test    eax, eax
0x180044586  js      loc_18004463B
0x18004458c  cmp     [rbp+pv], 0
0x180044590  jnz     loc_1800447CE
0x180044596  mov     r15d, 8
0x18004459c  mov     edx, r15d; cItemGrow
0x18004459f  lea     ecx, [r15+0Ch]; cbItem
0x1800445a3  call    cs:g_pfn_DSA_Create
0x1800445a9  mov     [rbp+hdsa], rax
0x1800445ad  mov     rbx, rax
0x1800445b0  test    rax, rax
0x1800445b3  jz      loc_18004473F
0x1800445b9  xor     esi, esi
0x1800445bb  xor     r14d, r14d
0x1800445be  xor     edi, edi
0x1800445c0  test    r14d, r14d
0x1800445c3  js      short loc_1800445F4
0x1800445c5  mov     rcx, [r13+20h]
0x1800445c9  lea     r8, [rbp+pitem]
0x1800445cd  xor     eax, eax
0x1800445cf  xorps   xmm0, xmm0
0x1800445d2  mov     dword ptr [rbp+var_18], eax
0x1800445d5  mov     edx, edi
0x1800445d7  movups  [rbp+pitem], xmm0
0x1800445db  mov     rax, [rcx]
0x1800445de  mov     rax, [rax+28h]
0x1800445e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800445e7  test    eax, eax
0x1800445e9  jns     loc_180044755
0x1800445ef  mov     rsi, rbx
0x1800445f2  xor     ebx, ebx
0x1800445f4  test    rbx, rbx
0x1800445f7  jz      short loc_180044602
0x1800445f9  mov     rcx, rbx; hdsa
0x1800445fc  call    cs:__imp_DSA_Destroy
0x180044602  test    r14d, r14d
0x180044605  js      short loc_18004463B
0x180044607  test    rsi, rsi
0x18004460a  jz      loc_18004476C
0x180044610  mov     eax, [rsi]
0x180044612  lea     rbx, [rax+rax*4]
0x180044616  mov     dword ptr [rbp+hdsa], eax
0x180044619  shl     rbx, 2
0x18004461d  mov     eax, 0FFFFFFFFh
0x180044622  cmp     rbx, rax
0x180044625  jbe     short loc_18004467F
0x180044627  mov     r14d, 80070216h
0x18004462d  test    rsi, rsi
0x180044630  jz      short loc_18004463B
0x180044632  mov     rcx, rsi; hdsa
0x180044635  call    cs:__imp_DSA_Destroy
0x18004463b  mov     rcx, [rbp+var_30]
0x18004463f  mov     [rbp+var_30], 0
0x180044647  test    rcx, rcx
0x18004464a  jz      short loc_180044658
0x18004464c  mov     rax, [rcx]
0x18004464f  mov     rax, [rax+10h]
0x180044653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044658  mov     eax, r14d
0x18004465b  mov     rcx, [rbp+var_10]
0x18004465f  xor     rcx, rsp; StackCookie
0x180044662  call    __security_check_cookie
0x180044667  mov     rbx, [rsp+70h+arg_10]
0x18004466f  add     rsp, 70h
0x180044673  pop     r15
0x180044675  pop     r14
0x180044677  pop     r13
0x180044679  pop     r12
0x18004467b  pop     rdi
0x18004467c  pop     rsi
0x18004467d  pop     rbp
0x18004467e  retn
0x18004467f  mov     r8d, 4; cb
0x180044685  lea     rdx, [rbp+hdsa]; pv
0x180044689  mov     rcx, r12; pstm
0x18004468c  call    cs:__imp_IStream_Write
0x180044692  mov     r14d, eax
0x180044695  test    eax, eax
0x180044697  js      short loc_18004462D
0x180044699  cmp     dword ptr [rbp+hdsa], 0
0x18004469d  jz      short loc_1800446C4
0x18004469f  xor     edx, edx; i
0x1800446a1  mov     rcx, rsi; hdsa
0x1800446a4  call    cs:g_pfn_DSA_GetItemPtr
0x1800446aa  mov     r8d, ebx; cb
0x1800446ad  mov     rcx, r12; pstm
0x1800446b0  mov     rdx, rax; pv
0x1800446b3  call    cs:__imp_IStream_Write
0x1800446b9  mov     r14d, eax
0x1800446bc  test    eax, eax
0x1800446be  js      loc_18004462D
0x1800446c4  mov     edx, r15d; cItemGrow
0x1800446c7  mov     ecx, 18h; cbItem
0x1800446cc  call    cs:g_pfn_DSA_Create
0x1800446d2  mov     rdi, rax
0x1800446d5  test    rax, rax
0x1800446d8  jz      short loc_18004474A
0x1800446da  xor     r14d, r14d
0x1800446dd  mov     ebx, 8007000Eh
0x1800446e2  xor     r15d, r15d
0x1800446e5  test    r14d, r14d
0x1800446e8  js      loc_1800447A1
0x1800446ee  mov     rcx, [r13+20h]
0x1800446f2  lea     r9, [rbp+var_18+4]
0x1800446f6  xor     eax, eax
0x1800446f8  lea     r8, [rbp+pitem]
0x1800446fc  mov     [rbp+var_18], rax
0x180044700  xorps   xmm0, xmm0
0x180044703  movups  [rbp+pitem], xmm0
0x180044707  mov     rax, [rcx]
0x18004470a  mov     edx, r15d
0x18004470d  mov     rax, [rax+38h]
0x180044711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044716  test    eax, eax
0x180044718  js      loc_180044886
0x18004471e  lea     r8, [rbp+pitem]; pitem
0x180044722  mov     edx, 7FFFFFFFh; i
0x180044727  mov     rcx, rdi; hdsa
0x18004472a  call    cs:__imp_DSA_InsertItem
0x180044730  xor     r14d, r14d
0x180044733  cmp     eax, 0FFFFFFFFh
0x180044736  cmovz   r14d, ebx
0x18004473a  inc     r15d
0x18004473d  jmp     short loc_1800446E5
0x18004473f  mov     r14d, 8007000Eh
0x180044745  jmp     loc_18004463B
0x18004474a  mov     r14d, 8007000Eh
0x180044750  jmp     loc_18004462D
0x180044755  lea     rdx, [rbp+pitem]
0x180044759  lea     rcx, [rbp+hdsa]
0x18004475d  call    ?AppendItem@?$CDSA_Base@U_tagpropertykey@@@@QEAAJPEBU_tagpropertykey@@PEAH@Z; CDSA_Base<_tagpropertykey>::AppendItem(_tagpropertykey const *,int *)
0x180044762  mov     r14d, eax
0x180044765  inc     edi
0x180044767  jmp     loc_1800445C0
0x18004476c  xor     eax, eax
0x18004476e  jmp     loc_180044612
0x180044773  mov     r8d, 4; cb
0x180044779  lea     rdx, [rbp+hdsa]; pv
0x18004477d  mov     rcx, r12; pstm
0x180044780  call    cs:__imp_IStream_Write
0x180044786  mov     r14d, eax
0x180044789  test    eax, eax
0x18004478b  js      short loc_180044793
0x18004478d  cmp     dword ptr [rbp+hdsa], 0
0x180044791  jnz     short loc_1800447AF
0x180044793  test    rbx, rbx
0x180044796  jz      short loc_1800447A1
0x180044798  mov     rcx, rbx; hdsa
0x18004479b  call    cs:__imp_DSA_Destroy
0x1800447a1  mov     rcx, rdi; hdsa
0x1800447a4  call    cs:__imp_DSA_Destroy
0x1800447aa  jmp     loc_18004462D
0x1800447af  xor     edx, edx; i
0x1800447b1  mov     rcx, rbx; hdsa
0x1800447b4  call    cs:g_pfn_DSA_GetItemPtr
0x1800447ba  mov     r8d, r15d; cb
0x1800447bd  mov     rcx, r12; pstm
0x1800447c0  mov     rdx, rax; pv
0x1800447c3  call    cs:__imp_IStream_Write
0x1800447c9  mov     r14d, eax
0x1800447cc  jmp     short loc_180044793
0x1800447ce  mov     r8, [rbp+var_30]; struct IUnknown *
0x1800447d2  mov     edx, 1; int
0x1800447d7  mov     rcx, r12; struct IStream *
0x1800447da  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x1800447df  mov     r14d, eax
0x1800447e2  test    eax, eax
0x1800447e4  jns     loc_180044596
0x1800447ea  jmp     loc_18004463B
0x1800447ef  mov     r8d, 4; cb
0x1800447f5  lea     rdx, [rbp+hdsa]; pv
0x1800447f9  mov     rcx, r12; pstm
0x1800447fc  call    cs:__imp_IStream_Write
0x180044802  mov     r14d, eax
0x180044805  test    eax, eax
0x180044807  js      short loc_1800447A1
0x180044809  cmp     dword ptr [rbp+hdsa], 0
0x18004480d  jz      short loc_180044834
0x18004480f  xor     edx, edx; i
0x180044811  mov     rcx, rdi; hdsa
0x180044814  call    cs:g_pfn_DSA_GetItemPtr
0x18004481a  mov     r8d, ebx; cb
0x18004481d  mov     rcx, r12; pstm
0x180044820  mov     rdx, rax; pv
0x180044823  call    cs:__imp_IStream_Write
0x180044829  mov     r14d, eax
0x18004482c  test    eax, eax
0x18004482e  js      loc_1800447A1
0x180044834  lea     rdx, [rbp+hdsa]
0x180044838  mov     [rbp+hdsa], 0
0x180044840  mov     rcx, r13
0x180044843  call    ?_GetRelevanceList@CBinaryAutoList@@AEAAJPEAV?$CDSA@U_tagpropertykey@@@@@Z; CBinaryAutoList::_GetRelevanceList(CDSA<_tagpropertykey> *)
0x180044848  mov     r14d, eax
0x18004484b  test    eax, eax
0x18004484d  js      loc_1800447A1
0x180044853  mov     rbx, [rbp+hdsa]
0x180044857  test    rbx, rbx
0x18004485a  jz      short loc_180044882
0x18004485c  mov     eax, [rbx]
0x18004485e  lea     r15, [rax+rax*4]
0x180044862  mov     dword ptr [rbp+hdsa], eax
0x180044865  shl     r15, 2
0x180044869  mov     eax, 0FFFFFFFFh
0x18004486e  cmp     r15, rax
0x180044871  jbe     loc_180044773
0x180044877  mov     r14d, 80070216h
0x18004487d  jmp     loc_180044793
0x180044882  xor     eax, eax
0x180044884  jmp     short loc_18004485E
0x180044886  mov     eax, [rdi]
0x180044888  mov     dword ptr [rbp+hdsa], eax
0x18004488b  lea     rbx, [rax+rax*2]
0x18004488f  mov     eax, 0FFFFFFFFh
0x180044894  shl     rbx, 3
0x180044898  cmp     rbx, rax
0x18004489b  jbe     loc_1800447EF
0x1800448a1  mov     r14d, 80070216h
0x1800448a7  jmp     loc_1800447A1
```
