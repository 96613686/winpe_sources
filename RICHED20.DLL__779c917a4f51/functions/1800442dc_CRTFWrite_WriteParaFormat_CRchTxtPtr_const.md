# CRTFWrite::WriteParaFormat(CRchTxtPtr const *)

- ea: `0x1800442dc`
- end: `0x180044b32`
- name: `?WriteParaFormat@CRTFWrite@@AEAAHPEBVCRchTxtPtr@@@Z`
- size: `2134`
- prototype: `__int64 __fastcall(CRTFWrite *__hidden this, const struct CRchTxtPtr *)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x180028064`

## callees

- `0x1800064d0`
- `0x180009860`
- `0x18001dfd0`
- `0x1800202a0`
- `0x180024910`
- `0x180028e40`
- `0x180029a40`
- `0x18002a144`
- `0x18002c900`
- `0x18003e260`
- `0x18003eed8`
- `0x18003ef9c`
- `0x18003f1b0`
- `0x1800425ec`
- `0x1800442dc`
- `0x180044ee0`
- `0x18004b728`
- `0x18007d5a0`
- `0x180091140`

## pseudocode

```c
__int64 __fastcall CRTFWrite::WriteParaFormat(CRTFWrite *this, const struct CRchTxtPtr *a2)
{
  const struct CParaFormat *v2; // rbp
  const struct CParaFormat *PF; // rax
  int *v6; // rsi
  __int16 v7; // r15
  unsigned __int8 v8; // r13
  signed int v9; // ebx
  int v10; // r14d
  signed int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  int v17; // edx
  __int16 v18; // bp
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  int EOP; // eax
  __int16 Format; // ax
  unsigned __int8 *CharFormat; // rbx
  int v24; // eax
  int v25; // r15d
  int v26; // r8d
  int v27; // r13d
  unsigned __int16 v28; // bx
  const char *v29; // r8
  unsigned __int16 v30; // r15
  int v31; // r15d
  unsigned int v32; // ebx
  unsigned int v33; // ebx
  const char *v34; // r8
  int v35; // ebp
  int v36; // r9d
  int v37; // r9d
  int v38; // r9d
  int v39; // r9d
  int v40; // r9d
  int v41; // ebx
  int v42; // ebx
  int v43; // ebp
  int v44; // r15d
  const int *v45; // r13
  signed int v46; // r14d
  int v47; // r12d
  unsigned __int8 v49; // [rsp+30h] [rbp-B8h]
  signed int v50; // [rsp+34h] [rbp-B4h]
  int v51; // [rsp+38h] [rbp-B0h]
  __int16 v52; // [rsp+3Ch] [rbp-ACh]
  __int128 v53; // [rsp+40h] [rbp-A8h] BYREF
  _OWORD v54[2]; // [rsp+50h] [rbp-98h] BYREF
  unsigned __int16 v55[24]; // [rsp+70h] [rbp-78h] BYREF

  v2 = (const struct CParaFormat *)*((_QWORD *)this + 29);
  PF = CRchTxtPtr::GetPF(a2);
  *((_QWORD *)this + 29) = PF;
  v6 = (int *)PF;
  v7 = *((_WORD *)PF + 1) & 0x4000;
  v8 = *((_BYTE *)PF + 34);
  v9 = *((unsigned __int8 *)PF + 17);
  v10 = *((_DWORD *)PF + 7);
  v52 = v7;
  v49 = v8;
  CRTFWrite::CheckInTable(this, 0);
  v11 = 0;
  if ( !v7 )
    v11 = v9;
  v50 = v11;
  if ( ((*((_BYTE *)this + 84) & 0x10) == 0 || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 180, 0))
    && (unsigned int)CRTFWrite::PutCtrlWord(this, 0, 150, 0)
    && ((*((_BYTE *)this + 84) & 0x10) == 0 || (unsigned int)CRTFWrite::PutCtrlWord(this, 0, 180, 0)) )
  {
    if ( v7 )
    {
      if ( *((_BYTE *)this + 145) && !(unsigned int)CRTFWrite::PutCtrlWord(this, 0, 107, 0) )
        return *((unsigned int *)this + 12);
    }
    else if ( (unsigned int)CRTFWrite::PutBorders(this, 0) )
    {
      return *((unsigned int *)this + 12);
    }
    if ( !*((_WORD *)v6 + 19)
      || ((v12 = *((unsigned __int16 *)v6 + 19), v13 = *((_WORD *)v6 + 19) & 0xF, (unsigned int)(v13 - 1) > 0xB)
       || (unsigned int)CRTFWrite::PutCtrlWord(this, 0, (unsigned __int8)aFbidis[v13 + 7], 0))
      && (((v12 >> 6) & 0x1F) == 0
       || (v14 = CRTFWrite::LookupColor(this, *((_DWORD *)&g_Colors + ((((v12 >> 6) & 0x1F) - 1) & 0xF))),
           (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 45, v14 + 1)))
      && ((v15 = v12 >> 11) == 0
       || (v16 = CRTFWrite::LookupColor(this, *((_DWORD *)&g_Colors + (((_BYTE)v15 - 1) & 0xF))),
           (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 41, v16 + 1))) )
    {
      if ( !*((_WORD *)v6 + 18) || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 207, *((unsigned __int16 *)v6 + 18)) )
      {
        v17 = *((_DWORD *)this + 55);
        *((_WORD *)this + 70) = 0;
        *((_DWORD *)this + 55) = CParaFormat::UpdateNumber((CParaFormat *)v6, v17, v2);
        if ( *(_WORD *)v6 )
        {
          v18 = *((_WORD *)v6 + 21) & 0xF00;
          if ( (unsigned int)*(unsigned __int16 *)v6 - 2 > 5 )
          {
            v33 = *((_DWORD *)this + 44);
            if ( !(unsigned int)CRTFWrite::printF(this, "{\\pntext\\f%d\\'B7\\tab}", v33) )
              return *((unsigned int *)this + 12);
            v34 = "cont";
            if ( v18 != 1024 )
              v34 = "blt";
            if ( !(unsigned int)CRTFWrite::printF(
                                  this,
                                  "{\\*\\pn\\pnlvl%s\\pnf%d\\pnindent%d{\\pntxtb\\'B7}}",
                                  v34,
                                  v33,
                                  *((unsigned __int16 *)v6 + 22)) )
              return *((unsigned int *)this + 12);
          }
          else
          {
            v19 = *((_OWORD *)a2 + 2);
            v54[0] = *((_OWORD *)a2 + 1);
            v20 = *((_OWORD *)a2 + 3);
            v54[1] = v19;
            v53 = v20;
            EOP = CTxtPtr::FindEOP((CTxtPtr *)v54, 0x3FFFFFFF, 0);
            CRunPtrBase::AdvanceCp((CRunPtrBase *)&v53, EOP);
            CRunPtrBase::AdjustBackward((CRunPtrBase *)&v53);
            Format = CFormatRunPtr::GetFormat((CFormatRunPtr *)&v53);
            CharFormat = (unsigned __int8 *)CTxtArray::GetCharFormat(
                                              (CTxtArray *)(*((_QWORD *)this + 7) + 248LL),
                                              Format);
            v24 = CRTFWrite::LookupFont(this, (const struct CCharFormat *)CharFormat);
            v25 = 0;
            if ( v24 >= 0 )
              v25 = v24;
            *((_DWORD *)this + 56) = v25;
            v51 = v25;
            *((_DWORD *)this + 57) = CW32System::GetCodePage(CharFormat[4]);
            v27 = v26;
            if ( *(_WORD *)v6 <= 6u )
              v27 = *(unsigned __int16 *)v6 - 2;
            if ( (v18 & 0xFEFF) != 0 )
            {
              v28 = 46;
              if ( v18 != 512 )
                v28 = v26;
            }
            else
            {
              v28 = 41;
            }
            if ( v18 != 1024 )
            {
              CParaFormat::NumToStr((CParaFormat *)v6, v55, *((_DWORD *)this + 55), 1u);
              if ( !(unsigned int)CRTFWrite::printF(this, "{\\pntext\\f%d ", v25)
                || (unsigned int)CRTFWrite::WritePcData(this, v55, *((_DWORD *)this + 57), 0)
                || !(unsigned int)CRTFWrite::printF(this, "\\tab}") )
              {
                return *((unsigned int *)this + 12);
              }
            }
            v29 = "cont";
            v30 = *((_WORD *)v6 + 21);
            if ( v18 != 1024 )
              v29 = "body";
            if ( !(unsigned int)CRTFWrite::printF(
                                  this,
                                  "{\\*\\pn\\pnlvl%s\\pnf%d\\pnindent%d\\pnstart%d",
                                  v29,
                                  v51,
                                  *((unsigned __int16 *)v6 + 22),
                                  *((unsigned __int16 *)v6 + 20)) )
              return *((unsigned int *)this + 12);
            v31 = v30 & 3;
            if ( (unsigned int)(v31 - 1) <= 1
              && !(unsigned int)CRTFWrite::PutCtrlWord(this, 0, (unsigned int)(v31 != 1) + 172, 0) )
            {
              return *((unsigned int *)this + 12);
            }
            if ( !(unsigned int)CRTFWrite::PutCtrlWord(this, 0, *((unsigned __int8 *)qword_180099D28 + v27), 0)
              || v18 == 256 && !(unsigned int)CRTFWrite::printF(this, "{\\pntxtb(}")
              || v28 && !(unsigned int)CRTFWrite::printF(this, "{\\pntxta%c}", v28)
              || !(unsigned int)CRTFWrite::printF(this, &szEndGroupCRLF) )
            {
              return *((unsigned int *)this + 12);
            }
            v7 = v52;
            v8 = v49;
          }
          *((_BYTE *)this + 140) = 1;
        }
        v32 = *((_WORD *)v6 + 1) & 0x1FF;
        if ( (*(_BYTE *)(*((_QWORD *)this + 7) + 192LL) & 1) == 0
          || (*((_BYTE *)v6 + 2) & 1) != 0
          || (unsigned int)CRTFWrite::PutCtrlWord(this, 0, 121, 0) )
        {
          v35 = 9;
          while ( v32 && v35 )
          {
            --v35;
            if ( (v32 & 1) != 0
              && !(unsigned int)CRTFWrite::PutCtrlWord(
                                  this,
                                  v35 == 2,
                                  *((unsigned __int8 *)&qword_180099D28[6] + v35),
                                  0) )
            {
              return *((unsigned int *)this + 12);
            }
            v32 >>= 1;
          }
          if ( ((unsigned __int16)(*((_WORD *)v6 + 16) + 10) > 8u
             || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 199, ~*((__int16 *)v6 + 16)))
            && (v7
             || ((v36 = v6[3]) == 0 || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 75, -v36))
             && ((v37 = v6[3] + v6[1]) == 0
              || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, (*((_BYTE *)v6 + 2) & 1) != 0 ? 191 : 114, v37))
             && ((v38 = v6[2]) == 0
              || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, (*((_BYTE *)v6 + 2) & 1) != 0 ? 114 : 191, v38))
             && ((v39 = v6[5]) == 0 || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 201, v39))
             && ((v40 = v6[6]) == 0 || (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 200, v40))) )
          {
            if ( !v8 )
              goto LABEL_107;
            v41 = 0;
            if ( v8 == 4 )
            {
              if ( v10 < 0 )
                v10 = -v10;
              v10 = -v10;
            }
            else if ( v8 == 5 )
            {
              v41 = 1;
              v10 *= 12;
            }
            else if ( v8 != 3 && v10 > 0 )
            {
              v41 = 1;
              if ( v8 <= 2u )
                v10 = 120 * (v8 + 2);
            }
            if ( (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 208, v10)
              && (unsigned int)CRTFWrite::PutCtrlWord(this, 1, 209, v41) )
            {
LABEL_107:
              if ( v7
                || (unsigned int)*((unsigned __int8 *)v6 + 16) - 2 > 2
                || (unsigned int)CRTFWrite::PutCtrlWord(
                                   this,
                                   0,
                                   *((unsigned __int8 *)&qword_180099D28[2] + *((unsigned __int8 *)v6 + 16) + 3),
                                   0) )
              {
                v42 = 0;
                v43 = 0;
                v44 = 0;
                v45 = CTabsArray::Deref(qword_1800A41E0, *((__int16 *)v6 + 9));
                v46 = 0;
                if ( v50 )
                {
                  do
                  {
                    if ( v46 < (unsigned int)*((unsigned __int8 *)v6 + 17) )
                    {
                      _mm_lfence();
                      v42 = (v45[v46] >> 24) & 0xF;
                      v44 = v45[v46] & 0xFFFFFF;
                      v43 = v45[v46] >> 28;
                    }
                    v47 = 215;
                    if ( v42 != 4 )
                    {
                      v47 = 234;
                      if ( v42 )
                      {
                        if ( !(unsigned int)CRTFWrite::PutCtrlWord(
                                              this,
                                              0,
                                              *((unsigned __int8 *)&qword_180099D28[1] + v42 + 7),
                                              0) )
                          break;
                      }
                    }
                    if ( v43
                      && !(unsigned int)CRTFWrite::PutCtrlWord(
                                          this,
                                          0,
                                          *((unsigned __int8 *)qword_180099D28 + v43 + 7),
                                          0) )
                    {
                      break;
                    }
                    if ( !(unsigned int)CRTFWrite::PutCtrlWord(this, 1, v47, v44) )
                      break;
                    ++v46;
                  }
                  while ( v46 < v50 );
                }
              }
            }
          }
        }
      }
    }
  }
  return *((unsigned int *)this + 12);
}

```

## disassembly

```asm
0x1800442dc  mov     [rsp+arg_10], rbx
0x1800442e1  push    rbp
0x1800442e2  push    rsi
0x1800442e3  push    rdi
0x1800442e4  push    r12
0x1800442e6  push    r13
0x1800442e8  push    r14
0x1800442ea  push    r15
0x1800442ec  sub     rsp, 0B0h
0x1800442f3  mov     rax, cs:__security_cookie
0x1800442fa  xor     rax, rsp
0x1800442fd  mov     [rsp+0E8h+var_48], rax
0x180044305  mov     rbp, [rcx+0E8h]
0x18004430c  mov     rdi, rcx
0x18004430f  mov     rcx, rdx; this
0x180044312  mov     r12, rdx
0x180044315  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x18004431a  mov     [rdi+0E8h], rax
0x180044321  mov     r15d, 4000h
0x180044327  xor     edx, edx; int
0x180044329  mov     rcx, rdi; this
0x18004432c  mov     rsi, rax
0x18004432f  and     r15w, [rax+2]
0x180044334  mov     r13b, [rax+22h]
0x180044338  movzx   ebx, byte ptr [rax+11h]
0x18004433c  mov     r14d, [rax+1Ch]
0x180044340  mov     [rsp+0E8h+var_AC], r15d
0x180044345  mov     [rsp+0E8h+var_B8], r13b
0x18004434a  call    ?CheckInTable@CRTFWrite@@AEAAHH@Z; CRTFWrite::CheckInTable(int)
0x18004434f  xor     ecx, ecx
0x180044351  test    r15w, r15w
0x180044355  mov     eax, ecx
0x180044357  cmovz   eax, ebx
0x18004435a  test    byte ptr [rdi+54h], 10h
0x18004435e  mov     [rsp+0E8h+var_B4], eax
0x180044362  jz      short loc_180044383
0x180044364  lea     edx, [rcx+1]; int
0x180044367  xor     r9d, r9d; int
0x18004436a  mov     rcx, rdi; this
0x18004436d  mov     r8d, 0B4h; int
0x180044373  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180044378  xor     ebx, ebx
0x18004437a  test    eax, eax
0x18004437c  jnz     short loc_180044385
0x18004437e  jmp     loc_180044B04
0x180044383  xor     ebx, ebx
0x180044385  xor     r9d, r9d; int
0x180044388  xor     edx, edx; int
0x18004438a  mov     r8d, 96h; int
0x180044390  mov     rcx, rdi; this
0x180044393  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180044398  test    eax, eax
0x18004439a  jz      loc_180044B04
0x1800443a0  test    byte ptr [rdi+54h], 10h
0x1800443a4  jz      short loc_1800443C1
0x1800443a6  xor     r9d, r9d; int
0x1800443a9  xor     edx, edx; int
0x1800443ab  mov     r8d, 0B4h; int
0x1800443b1  mov     rcx, rdi; this
0x1800443b4  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x1800443b9  test    eax, eax
0x1800443bb  jz      loc_180044B04
0x1800443c1  test    r15w, r15w
0x1800443c5  jz      short loc_1800443E9
0x1800443c7  cmp     [rdi+91h], bl
0x1800443cd  jz      short loc_1800443FB
0x1800443cf  xor     r9d, r9d; int
0x1800443d2  xor     edx, edx; int
0x1800443d4  mov     rcx, rdi; this
0x1800443d7  lea     r8d, [r9+6Bh]; int
0x1800443db  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x1800443e0  test    eax, eax
0x1800443e2  jnz     short loc_1800443FB
0x1800443e4  jmp     loc_180044B04
0x1800443e9  xor     edx, edx; int
0x1800443eb  mov     rcx, rdi; this
0x1800443ee  call    ?PutBorders@CRTFWrite@@AEAAHH@Z; CRTFWrite::PutBorders(int)
0x1800443f3  test    eax, eax
0x1800443f5  jnz     loc_180044B04
0x1800443fb  lea     r8, cs:180000000h
0x180044402  cmp     [rsi+26h], bx
0x180044406  jz      loc_1800444C6
0x18004440c  movzx   ebx, word ptr [rsi+26h]
0x180044410  mov     ecx, ebx
0x180044412  and     ecx, 0Fh
0x180044415  lea     eax, [rcx-1]
0x180044418  cmp     eax, 0Bh
0x18004441b  ja      short loc_180044442
0x18004441d  movzx   r8d, byte ptr [rcx+r8+99CFFh]; int
0x180044426  xor     r9d, r9d; int
0x180044429  mov     rcx, rdi; this
0x18004442c  xor     edx, edx; int
0x18004442e  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180044433  test    eax, eax
0x180044435  jz      loc_180044B04
0x18004443b  lea     r8, cs:180000000h
0x180044442  mov     eax, ebx
0x180044444  shr     eax, 6
0x180044447  and     eax, 1Fh
0x18004444a  jz      short loc_180044480
0x18004444c  lea     rdx, [rax-1]
0x180044450  mov     rcx, rdi; this
0x180044453  and     edx, 0Fh
0x180044456  mov     edx, ds:rva ?g_Colors@@3QBKB[r8+rdx*4]; unsigned int
0x18004445e  call    ?LookupColor@CRTFWrite@@AEAAJK@Z; CRTFWrite::LookupColor(ulong)
0x180044463  mov     edx, 1; int
0x180044468  mov     rcx, rdi; this
0x18004446b  lea     r9d, [rax+1]; int
0x18004446f  lea     r8d, [rdx+2Ch]; int
0x180044473  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180044478  test    eax, eax
0x18004447a  jz      loc_180044B04
0x180044480  shr     ebx, 0Bh
0x180044483  test    ebx, ebx
0x180044485  jz      short loc_1800444C4
0x180044487  lea     rdx, [rbx-1]
0x18004448b  mov     rcx, rdi; this
0x18004448e  and     edx, 0Fh
0x180044491  lea     rax, cs:180000000h
0x180044498  mov     edx, ds:rva ?g_Colors@@3QBKB[rax+rdx*4]; unsigned int
0x18004449f  call    ?LookupColor@CRTFWrite@@AEAAJK@Z; CRTFWrite::LookupColor(ulong)
0x1800444a4  mov     edx, 1; int
0x1800444a9  mov     rcx, rdi; this
0x1800444ac  lea     r9d, [rax+1]; int
0x1800444b0  lea     r8d, [rdx+28h]; int
0x1800444b4  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x1800444b9  xor     ebx, ebx
0x1800444bb  test    eax, eax
0x1800444bd  jnz     short loc_1800444C6
0x1800444bf  jmp     loc_180044B04
0x1800444c4  xor     ebx, ebx
0x1800444c6  cmp     [rsi+24h], bx
0x1800444ca  jz      short loc_1800444EC
0x1800444cc  movzx   r9d, word ptr [rsi+24h]; int
0x1800444d1  mov     edx, 1; int
0x1800444d6  mov     r8d, 0CFh; int
0x1800444dc  mov     rcx, rdi; this
0x1800444df  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x1800444e4  test    eax, eax
0x1800444e6  jz      loc_180044B04
0x1800444ec  mov     edx, [rdi+0DCh]; int
0x1800444f2  mov     r8, rbp; struct CParaFormat *
0x1800444f5  mov     rcx, rsi; this
0x1800444f8  mov     word ptr [rdi+8Ch], 0
0x180044501  call    ?UpdateNumber@CParaFormat@@QEBAJJPEBV1@@Z; CParaFormat::UpdateNumber(long,CParaFormat const *)
0x180044506  mov     [rdi+0DCh], eax
0x18004450c  cmp     [rsi], bx
0x18004450f  jz      loc_180044784
0x180044515  movzx   eax, word ptr [rsi]
0x180044518  mov     ebp, 0F00h
0x18004451d  and     bp, [rsi+2Ah]
0x180044521  sub     eax, 2
0x180044524  cmp     eax, 5
0x180044527  ja      loc_1800447C5
0x18004452d  movups  xmm0, xmmword ptr [r12+10h]
0x180044533  xor     r8d, r8d; int *
0x180044536  mov     edx, 3FFFFFFFh; int
0x18004453b  movups  xmm1, xmmword ptr [r12+20h]
0x180044541  lea     rcx, [rsp+0E8h+var_98]; this
0x180044546  movups  [rsp+0E8h+var_98], xmm0
0x18004454b  movups  xmm0, xmmword ptr [r12+30h]
0x180044551  movups  [rsp+0E8h+var_88], xmm1
0x180044556  movdqu  [rsp+0E8h+var_A8], xmm0
0x18004455c  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x180044561  mov     edx, eax; int
0x180044563  lea     rcx, [rsp+0E8h+var_A8]; this
0x180044568  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18004456d  lea     rcx, [rsp+0E8h+var_A8]; this
0x180044572  call    ?AdjustBackward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustBackward(void)
0x180044577  lea     rcx, [rsp+0E8h+var_A8]; this
0x18004457c  call    ?GetFormat@CFormatRunPtr@@QEBAFXZ; CFormatRunPtr::GetFormat(void)
0x180044581  mov     rcx, [rdi+38h]
0x180044585  add     rcx, 0F8h; this
0x18004458c  movsx   edx, ax; int
0x18004458f  call    ?GetCharFormat@CTxtArray@@QEAAPEBVCCharFormat@@J@Z; CTxtArray::GetCharFormat(long)
0x180044594  mov     rdx, rax; struct CCharFormat *
0x180044597  mov     rcx, rdi; this
0x18004459a  mov     rbx, rax
0x18004459d  call    ?LookupFont@CRTFWrite@@AEAAJPEBVCCharFormat@@@Z; CRTFWrite::LookupFont(CCharFormat const *)
0x1800445a2  xor     r8d, r8d
0x1800445a5  test    eax, eax
0x1800445a7  mov     r15d, r8d
0x1800445aa  cmovns  r15d, eax
0x1800445ae  mov     [rdi+0E0h], r15d
0x1800445b5  mov     cl, [rbx+4]; unsigned __int8
0x1800445b8  mov     [rsp+0E8h+var_B0], r15d
0x1800445bd  call    ?GetCodePage@CW32System@@SAHE@Z; CW32System::GetCodePage(uchar)
0x1800445c2  mov     [rdi+0E4h], eax
0x1800445c8  mov     r13d, r8d
0x1800445cb  cmp     word ptr [rsi], 6
0x1800445cf  ja      short loc_1800445D9
0x1800445d1  movzx   r13d, word ptr [rsi]
0x1800445d5  sub     r13d, 2
0x1800445d9  mov     eax, 0FEFFh
0x1800445de  test    ax, bp
0x1800445e1  jz      short loc_1800445F7
0x1800445e3  mov     ecx, 200h
0x1800445e8  mov     ebx, 2Eh ; '.'
0x1800445ed  cmp     bp, cx
0x1800445f0  cmovnz  bx, r8w
0x1800445f5  jmp     short loc_1800445FC
0x1800445f7  mov     ebx, 29h ; ')'
0x1800445fc  mov     r12d, 400h
0x180044602  cmp     bp, r12w
0x180044606  jz      short loc_180044675
0x180044608  mov     r8d, [rdi+0DCh]; int
0x18004460f  lea     rdx, [rsp+0E8h+var_78]; unsigned __int16 *
0x180044614  mov     r9d, 1; unsigned int
0x18004461a  mov     rcx, rsi; this
0x18004461d  call    ?NumToStr@CParaFormat@@QEBAJPEAGJK@Z; CParaFormat::NumToStr(ushort *,long,ulong)
0x180044622  mov     r8d, r15d
0x180044625  lea     rdx, aPntextFD; "{\\pntext\\f%d "
0x18004462c  mov     rcx, rdi; this
0x18004462f  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x180044634  xor     r15d, r15d
0x180044637  test    eax, eax
0x180044639  jz      loc_180044B04
0x18004463f  mov     r8d, [rdi+0E4h]; unsigned int
0x180044646  lea     rdx, [rsp+0E8h+var_78]; unsigned __int16 *
0x18004464b  xor     r9d, r9d; int
0x18004464e  mov     rcx, rdi; this
0x180044651  call    ?WritePcData@CRTFWrite@@AEAAHPEBGHH@Z; CRTFWrite::WritePcData(ushort const *,int,int)
0x180044656  test    eax, eax
0x180044658  jnz     loc_180044B04
0x18004465e  lea     rdx, aTab_0; "\\tab}"
0x180044665  mov     rcx, rdi; this
0x180044668  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x18004466d  test    eax, eax
0x18004466f  jz      loc_180044B04
0x180044675  movzx   ecx, word ptr [rsi+2Ch]
0x180044679  lea     rdx, aBody; "body"
0x180044680  movzx   eax, word ptr [rsi+28h]
0x180044684  lea     r8, aCont; "cont"
0x18004468b  mov     r9d, [rsp+0E8h+var_B0]
0x180044690  cmp     bp, r12w
0x180044694  movzx   r15d, word ptr [rsi+2Ah]
0x180044699  mov     [rsp+0E8h+var_C0], eax
0x18004469d  cmovnz  r8, rdx
0x1800446a1  mov     [rsp+0E8h+var_C8], ecx
0x1800446a5  lea     rdx, aPnPnlvlSPnfDPn; "{\\*\\pn\\pnlvl%s\\pnf%d\\pnindent%d\\p"...
0x1800446ac  mov     rcx, rdi; this
0x1800446af  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x1800446b4  xor     r12d, r12d
0x1800446b7  test    eax, eax
0x1800446b9  jz      loc_180044B04
0x1800446bf  and     r15d, 3
0x1800446c3  lea     eax, [r15-1]
0x1800446c7  cmp     eax, 1
0x1800446ca  ja      short loc_1800446F3
0x1800446cc  mov     r8d, r12d
0x1800446cf  cmp     r15d, 1
0x1800446d3  mov     rcx, rdi; this
0x1800446d6  setnz   r8b
0x1800446da  xor     r9d, r9d; int
0x1800446dd  add     r8d, 0ACh; int
0x1800446e4  xor     edx, edx; int
0x1800446e6  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x1800446eb  test    eax, eax
0x1800446ed  jz      loc_180044B04
0x1800446f3  movsxd  rax, r13d
0x1800446f6  lea     rcx, cs:180000000h
0x1800446fd  xor     r9d, r9d; int
0x180044700  xor     edx, edx; int
0x180044702  movzx   r8d, byte ptr [rax+rcx+99D28h]; int
0x18004470b  mov     rcx, rdi; this
0x18004470e  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180044713  test    eax, eax
0x180044715  jz      loc_180044B04
0x18004471b  mov     eax, 100h
0x180044720  cmp     bp, ax
0x180044723  jnz     short loc_18004473C
0x180044725  lea     rdx, aPntxtb_0; "{\\pntxtb(}"
0x18004472c  mov     rcx, rdi; this
0x18004472f  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x180044734  test    eax, eax
0x180044736  jz      loc_180044B04
0x18004473c  test    bx, bx
0x18004473f  jz      short loc_18004475C
0x180044741  movzx   r8d, bx
0x180044745  lea     rdx, aPntxtaC; "{\\pntxta%c}"
0x18004474c  mov     rcx, rdi; this
0x18004474f  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x180044754  test    eax, eax
0x180044756  jz      loc_180044B04
0x18004475c  lea     rdx, ?szEndGroupCRLF@@3QBDB; Format
0x180044763  mov     rcx, rdi; this
0x180044766  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x18004476b  test    eax, eax
0x18004476d  jz      loc_180044B04
0x180044773  mov     r15d, [rsp+0E8h+var_AC]
0x180044778  mov     r13b, [rsp+0E8h+var_B8]
0x18004477d  mov     byte ptr [rdi+8Ch], 1
0x180044784  mov     rax, [rdi+38h]
0x180044788  movzx   ebx, word ptr [rsi+2]
0x18004478c  and     ebx, 1FFh
0x180044792  test    byte ptr [rax+0C0h], 1
0x180044799  jz      loc_180044828
0x18004479f  test    bl, 1
0x1800447a2  jnz     loc_180044828
0x1800447a8  xor     r9d, r9d; int
  ... truncated ...
```
