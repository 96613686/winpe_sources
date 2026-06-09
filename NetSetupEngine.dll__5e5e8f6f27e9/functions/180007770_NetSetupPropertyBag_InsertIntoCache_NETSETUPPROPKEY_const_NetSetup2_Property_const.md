# NetSetupPropertyBag::InsertIntoCache(_NETSETUPPROPKEY const &,NetSetup2::Property const *)

- ea: `0x180007770`
- end: `0x1800079d4`
- name: `?InsertIntoCache@NetSetupPropertyBag@@AEBAXAEBU_NETSETUPPROPKEY@@PEBVProperty@NetSetup2@@@Z`
- size: `612`
- prototype: `void __fastcall(NetSetupPropertyBag *__hidden this, const struct _NETSETUPPROPKEY *, const struct Property *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001ef74`

## callees

- `0x1800076c0`
- `0x180007770`
- `0x1800086b0`
- `0x180009440`
- `0x180020898`
- `0x1800647e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800078fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800078fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800077b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800077b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800077be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800077be`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall NetSetupPropertyBag::InsertIntoCache(
        RTL_SRWLOCK *this,
        const struct _NETSETUPPROPKEY *a2,
        const struct Property *a3)
{
  int v6; // r9d
  RTL_SRWLOCK *v7; // rbp
  _BYTE *Ptr; // rdx
  _BYTE *v9; // r11
  _QWORD *v10; // rax
  _QWORD *v11; // rcx
  __int64 v12; // r8
  _BYTE *v13; // r8
  _DWORD *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  _QWORD *v17; // rdx
  __int128 v18; // [rsp+20h] [rbp-58h]

  v6 = *((_DWORD *)a2 + 4);
  if ( v6 != 8 )
    goto LABEL_29;
  v15 = *(_QWORD *)a2 - NETSETUPPKEY_Interface_NetLuidIndex;
  if ( *(_QWORD *)a2 == (_QWORD)NETSETUPPKEY_Interface_NetLuidIndex )
    v15 = *((_QWORD *)a2 + 1) - *((_QWORD *)&NETSETUPPKEY_Interface_NetLuidIndex + 1);
  if ( v15 )
  {
LABEL_29:
    if ( v6 != 6 )
      goto LABEL_3;
    v16 = *(_QWORD *)a2 - NETSETUPPKEY_INF_Characteristics;
    if ( *(_QWORD *)a2 == NETSETUPPKEY_INF_Characteristics )
      v16 = *((_QWORD *)a2 + 1) - 0x17957FBBAD0689ALL;
    if ( v16 )
    {
LABEL_3:
      v7 = this + 6;
      AcquireSRWLockExclusive(this + 6);
      LODWORD(v7[1].Ptr) = GetCurrentThreadId();
      Ptr = this[9].Ptr;
      v9 = this[8].Ptr;
      v10 = v9;
      v18 = *(_OWORD *)a2;
      if ( v9 != Ptr )
      {
        do
        {
          if ( *((_DWORD *)v10 + 4) == *((_DWORD *)a2 + 4) )
          {
            v12 = *v10 - v18;
            if ( *v10 == (_QWORD)v18 )
              v12 = v10[1] - *((_QWORD *)&v18 + 1);
            if ( !v12 )
              break;
          }
          v10 += 6;
        }
        while ( v10 != (_QWORD *)Ptr );
      }
      if ( v10 == (_QWORD *)Ptr )
        v11 = *(_QWORD **)a2;
      else
        v11 = v10;
      if ( v10 == (_QWORD *)Ptr )
      {
        if ( a3 )
        {
          v13 = this[10].Ptr;
          if ( Ptr == v13 && !(0xAAAAAAAAAAAAAAABuLL * ((v13 - Ptr) >> 4)) )
          {
            if ( 0xAAAAAAAAAAAAAAABuLL * ((Ptr - v9) >> 4) == 0x555555555555555LL )
              std::_Xlength_error("vector<T> too long");
            std::vector<NetSetup2::Property>::_Reallocate(&this[8]);
          }
          v14 = this[9].Ptr;
          *(_OWORD *)v14 = *(_OWORD *)&a3->lpVtbl;
          v14[4] = a3[2].lpVtbl;
          v14[5] = HIDWORD(a3[2].lpVtbl);
          std::vector<unsigned char>::vector<unsigned char>(v14 + 6, &a3[3]);
        }
        else
        {
          if ( Ptr == this[10].Ptr )
            std::vector<NetSetup2::Property>::_Reserve(&this[8]);
          v17 = this[9].Ptr;
          *(_OWORD *)v17 = *(_OWORD *)a2;
          v17[2] = *((unsigned int *)a2 + 4);
          v17[3] = 0;
          v17[4] = 0;
          v17[5] = 0;
        }
        this[9].Ptr = (char *)this[9].Ptr + 48;
      }
      else if ( a3 )
      {
        *(_OWORD *)v11 = *(_OWORD *)&a3->lpVtbl;
        *((_DWORD *)v11 + 4) = a3[2].lpVtbl;
        *((_DWORD *)v11 + 5) = HIDWORD(a3[2].lpVtbl);
        std::vector<unsigned char>::operator=(v11 + 3, &a3[3]);
      }
      else
      {
        *((_DWORD *)v11 + 5) = 0;
        v11[4] = v11[3];
      }
      LODWORD(v7[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v7);
    }
  }
}

```

## disassembly

```asm
0x180007770  mov     rax, rsp
0x180007773  push    rsi
0x180007774  push    rdi
0x180007775  push    r14
0x180007777  sub     rsp, 60h
0x18000777b  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180007783  mov     [rax+10h], rbx
0x180007787  mov     [rax+20h], rbp
0x18000778b  mov     rdi, r8
0x18000778e  mov     rsi, rdx
0x180007791  mov     rbx, rcx
0x180007794  mov     r9d, [rdx+10h]
0x180007798  cmp     r9d, 8
0x18000779c  jz      loc_180007915
0x1800077a2  cmp     r9d, 6
0x1800077a6  jz      loc_180007936
0x1800077ac  lea     rbp, [rcx+30h]
0x1800077b0  mov     [rsp+78h+var_28], rbp
0x1800077b5  mov     rcx, rbp; SRWLock
0x1800077b8  call    cs:__imp_AcquireSRWLockExclusive
0x1800077be  call    cs:__imp_GetCurrentThreadId
0x1800077c4  mov     [rbp+8], eax
0x1800077c7  mov     [rsp+78h+var_30], 2
0x1800077cf  mov     rdx, [rbx+48h]
0x1800077d3  mov     r11, [rbx+40h]
0x1800077d7  mov     rax, r11
0x1800077da  movups  xmm0, xmmword ptr [rsi]
0x1800077dd  movaps  [rsp+78h+var_58], xmm0
0x1800077e2  mov     ecx, [rsi+10h]
0x1800077e5  cmp     r11, rdx
0x1800077e8  jz      short loc_180007802
0x1800077ea  mov     r9, qword ptr [rsp+78h+var_58+8]
0x1800077ef  mov     r10, qword ptr [rsp+78h+var_58]
0x1800077f4  cmp     [rax+10h], ecx
0x1800077f7  jz      short loc_180007816
0x1800077f9  add     rax, 30h ; '0'
0x1800077fd  cmp     rax, rdx
0x180007800  jnz     short loc_1800077F4
0x180007802  cmp     rax, rdx
0x180007805  jz      short loc_18000782C
0x180007807  mov     byte ptr [rsp+78h+var_58+8], 1
0x18000780c  mov     rcx, rax
0x18000780f  mov     qword ptr [rsp+78h+var_58], rax
0x180007814  jmp     short loc_180007836
0x180007816  mov     r8, [rax]
0x180007819  sub     r8, r10
0x18000781c  jnz     short loc_180007825
0x18000781e  mov     r8, [rax+8]
0x180007822  sub     r8, r9
0x180007825  test    r8, r8
0x180007828  jz      short loc_180007802
0x18000782a  jmp     short loc_1800077F9
0x18000782c  mov     byte ptr [rsp+78h+var_58+8], 0
0x180007831  mov     rcx, qword ptr [rsp+78h+var_58]
0x180007836  xor     r14d, r14d
0x180007839  cmp     rax, rdx
0x18000783c  jnz     loc_18000798D
0x180007842  test    rdi, rdi
0x180007845  jz      loc_180007957
0x18000784b  mov     r8, [rbx+50h]
0x18000784f  cmp     rdx, r8
0x180007852  jnz     short loc_1800078CB
0x180007854  mov     rax, r8
0x180007857  sub     rax, rdx
0x18000785a  sar     rax, 4
0x18000785e  mov     rcx, 0AAAAAAAAAAAAAAABh
0x180007868  imul    rax, rcx
0x18000786c  cmp     rax, 1
0x180007870  jnb     short loc_1800078CB
0x180007872  sub     rdx, r11
0x180007875  sar     rdx, 4
0x180007879  imul    rdx, rcx
0x18000787d  mov     r9, 555555555555555h
0x180007887  mov     rax, r9
0x18000788a  sub     rax, rdx
0x18000788d  cmp     rax, 1
0x180007891  jb      loc_1800079C7
0x180007897  inc     rdx
0x18000789a  sub     r8, r11
0x18000789d  sar     r8, 4
0x1800078a1  imul    r8, rcx
0x1800078a5  mov     rax, r8
0x1800078a8  shr     rax, 1
0x1800078ab  sub     r9, rax
0x1800078ae  add     rax, r8
0x1800078b1  mov     ecx, r14d
0x1800078b4  cmp     r9, r8
0x1800078b7  cmovnb  rcx, rax
0x1800078bb  cmp     rcx, rdx
0x1800078be  cmovnb  rdx, rcx
0x1800078c2  lea     rcx, [rbx+40h]
0x1800078c6  call    ?_Reallocate@?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@IEAAX_K@Z; std::vector<NetSetup2::Property>::_Reallocate(unsigned __int64)
0x1800078cb  mov     rcx, [rbx+48h]
0x1800078cf  movups  xmm0, xmmword ptr [rdi]
0x1800078d2  movups  xmmword ptr [rcx], xmm0
0x1800078d5  mov     eax, [rdi+10h]
0x1800078d8  mov     [rcx+10h], eax
0x1800078db  mov     eax, [rdi+14h]
0x1800078de  mov     [rcx+14h], eax
0x1800078e1  lea     rdx, [rdi+18h]
0x1800078e5  add     rcx, 18h
0x1800078e9  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x1800078ee  add     qword ptr [rbx+48h], 30h ; '0'
0x1800078f3  mov     [rbp+8], r14d
0x1800078f7  mov     rcx, rbp; SRWLock
0x1800078fa  call    cs:__imp_ReleaseSRWLockExclusive
0x180007900  lea     r11, [rsp+78h+var_18]
0x180007905  mov     rbx, [r11+28h]
0x180007909  mov     rbp, [r11+38h]
0x18000790d  mov     rsp, r11
0x180007910  pop     r14
0x180007912  pop     rdi
0x180007913  pop     rsi
0x180007914  retn
0x180007915  mov     rax, [rdx]
0x180007918  sub     rax, qword ptr cs:NETSETUPPKEY_Interface_NetLuidIndex
0x18000791f  jnz     short loc_18000792C
0x180007921  mov     rax, [rdx+8]
0x180007925  sub     rax, qword ptr cs:NETSETUPPKEY_Interface_NetLuidIndex+8
0x18000792c  test    rax, rax
0x18000792f  jz      short loc_180007900
0x180007931  jmp     loc_1800077A2
0x180007936  mov     rax, [rdx]
0x180007939  sub     rax, cs:NETSETUPPKEY_INF_Characteristics
0x180007940  jnz     short loc_18000794D
0x180007942  mov     rax, [rdx+8]
0x180007946  sub     rax, cs:qword_1800999D8
0x18000794d  test    rax, rax
0x180007950  jz      short loc_180007900
0x180007952  jmp     loc_1800077AC
0x180007957  cmp     rdx, [rbx+50h]
0x18000795b  jz      short loc_180007982
0x18000795d  mov     rdx, [rbx+48h]
0x180007961  movups  xmm0, xmmword ptr [rsi]
0x180007964  movups  xmmword ptr [rdx], xmm0
0x180007967  mov     eax, [rsi+10h]
0x18000796a  mov     [rdx+10h], eax
0x18000796d  mov     [rdx+14h], r14d
0x180007971  mov     [rdx+18h], r14
0x180007975  mov     [rdx+20h], r14
0x180007979  mov     [rdx+28h], r14
0x18000797d  jmp     loc_1800078EE
0x180007982  lea     rcx, [rbx+40h]
0x180007986  call    ?_Reserve@?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@IEAAX_K@Z; std::vector<NetSetup2::Property>::_Reserve(unsigned __int64)
0x18000798b  jmp     short loc_18000795D
0x18000798d  test    rdi, rdi
0x180007990  jz      short loc_1800079B6
0x180007992  movups  xmm0, xmmword ptr [rdi]
0x180007995  movups  xmmword ptr [rcx], xmm0
0x180007998  mov     eax, [rdi+10h]
0x18000799b  mov     [rcx+10h], eax
0x18000799e  mov     eax, [rdi+14h]
0x1800079a1  mov     [rcx+14h], eax
0x1800079a4  lea     rdx, [rdi+18h]
0x1800079a8  add     rcx, 18h
0x1800079ac  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x1800079b1  jmp     loc_1800078F3
0x1800079b6  mov     [rcx+14h], r14d
0x1800079ba  mov     rax, [rcx+18h]
0x1800079be  mov     [rcx+20h], rax
0x1800079c2  jmp     loc_1800078F3
0x1800079c7  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x1800079ce  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
