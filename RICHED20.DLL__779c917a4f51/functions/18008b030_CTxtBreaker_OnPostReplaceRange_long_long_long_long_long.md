# CTxtBreaker::OnPostReplaceRange(long,long,long,long,long)

- ea: `0x18008b030`
- end: `0x18008b444`
- name: `?OnPostReplaceRange@CTxtBreaker@@UEAAXJJJJJ@Z`
- size: `1044`
- prototype: `void(CTxtBreaker *__hidden this, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x180008e90`
- `0x180008f04`
- `0x18001d8b0`
- `0x180023010`
- `0x180026758`
- `0x180026d10`
- `0x1800288d0`
- `0x1800395ec`
- `0x18008188c`
- `0x18008ab00`
- `0x18008adf4`
- `0x18008b030`
- `0x18008b684`
- `0x18008b738`
- `0x180091140`

## import_xrefs

- `USP10!ScriptBreak` at `0x18008b331`
- `USP10!ScriptBreak` at `0x18008b331`

## pseudocode

```c
void __fastcall CTxtBreaker::OnPostReplaceRange(CTxtBreaker *this, int a2, int a3, int a4)
{
  int v6; // edi
  int v8; // r15d
  CUniscribe *v9; // rax
  int v10; // r13d
  CBreakArray *v11; // r14
  CBreakArray **v12; // rax
  int v13; // r11d
  int v14; // r11d
  int v15; // edi
  int v16; // r14d
  CBreakArray *v17; // rcx
  CUniscribe *v18; // rcx
  int v19; // r8d
  int v20; // r14d
  SCRIPT_LOGATTR *v21; // r14
  CBreakArray *v22; // rcx
  CBreakArray **v23; // r13
  unsigned __int8 *v24; // rcx
  __int64 v25; // r12
  SCRIPT_LOGATTR **v26; // rax
  int v27; // eax
  __int64 v28; // rsi
  const SCRIPT_ANALYSIS *v29; // rdi
  const struct SCRIPT_PROPERTIES *v30; // rax
  unsigned int v31; // r8d
  int v32; // edi
  int v33; // eax
  __int64 v34; // rdi
  SCRIPT_LOGATTR *v35; // r15
  int v36; // r12d
  CBreakArray *v37; // rcx
  int v38; // r8d
  int v39; // eax
  CBreakArray *v40; // rcx
  _DWORD *v41; // rdi
  int v42; // [rsp+50h] [rbp-B0h] BYREF
  int v43; // [rsp+54h] [rbp-ACh] BYREF
  int v44; // [rsp+58h] [rbp-A8h]
  void *lpMem; // [rsp+60h] [rbp-A0h] BYREF
  int v46; // [rsp+68h] [rbp-98h]
  CBreakArray **v47; // [rsp+70h] [rbp-90h]
  SCRIPT_LOGATTR *psla; // [rsp+78h] [rbp-88h]
  CUniscribe *Uniscribe; // [rsp+80h] [rbp-80h]
  __int64 v50; // [rsp+88h] [rbp-78h]
  _BYTE v51[16]; // [rsp+90h] [rbp-70h] BYREF
  int v52; // [rsp+A0h] [rbp-60h]
  unsigned __int8 v53[512]; // [rsp+B0h] [rbp-50h] BYREF

  v44 = a2;
  psla = (SCRIPT_LOGATTR *)this;
  v6 = a2;
  if ( !a3 && !a4 )
    return;
  CTxtPtr::CTxtPtr((CTxtPtr *)v51, *((struct CTxtEdit **)this + 2), a2);
  if ( v6 <= 0 )
  {
    v8 = 0;
    v46 = 0;
  }
  else
  {
    v8 = v6 - 1;
    v46 = v6 - 1;
  }
  LODWORD(lpMem) = 0;
  v43 = 0;
  CTxtPtr::FindWhiteSpaceBound((CTxtPtr *)v51, a4, (int *)&lpMem, &v43, 0);
  v9 = (CUniscribe *)*((_QWORD *)this + 3);
  Uniscribe = v9;
  if ( v9 )
  {
    v42 = 1;
    v47 = (CBreakArray **)((char *)this + 32);
    v10 = 3;
    v11 = v9;
  }
  else
  {
    v12 = (CBreakArray **)((char *)this + 32);
    v10 = 1;
    v11 = *v12;
    v47 = v12;
    if ( !v11 )
    {
      v47 = v12;
      v11 = 0;
      v42 = 1;
      goto LABEL_15;
    }
    v42 = 0;
  }
  while ( v8 > (int)lpMem && ((unsigned int)CBreakArray::GetBreak(v11, v8) != v42 || v13) )
    v46 = --v8;
LABEL_15:
  CTxtPtr::AdvanceCp((CTxtPtr *)v51, v8 - v52);
  v14 = a3 + v6;
  v43 += a3 - a4;
  if ( v11 )
  {
    v15 = v43;
    while ( v14 < v15 )
    {
      if ( (unsigned int)CBreakArray::GetBreak(v11, v14) == v42 )
      {
        if ( !v10 )
          break;
        --v10;
      }
      ++v14;
    }
    v6 = v44;
  }
  v16 = v14 + a4 - a3;
  if ( v8 == v16 )
  {
    if ( Uniscribe )
      CBreakArray::ReplaceBreak(Uniscribe, v6, a3, 0);
    v17 = *(CBreakArray **)&psla[32];
    if ( v17 )
      CBreakArray::ReplaceBreak(v17, v6, a3, 0);
    return;
  }
  lpMem = 0;
  v42 = 0;
  Uniscribe = GetUniscribe();
  if ( !Uniscribe )
    return;
  v20 = v16 - v8;
  CUniscribe::CreateClientStruc(v18, v53, v19, (struct tagUSP_CLIENT **)&lpMem, v20, 7u);
  if ( !lpMem )
    return;
  CTxtPtr::GetText((CTxtPtr *)v51, v20, **(unsigned __int16 ***)lpMem);
  if ( (int)CUniscribe::ItemizeString(
              *(CUniscribe **)lpMem,
              (struct tagUSP_CLIENT *)lpMem,
              0,
              &v42,
              **(WCHAR ***)lpMem,
              v20,
              0,
              0,
              0) > 0 )
  {
    v21 = psla;
    v22 = *(CBreakArray **)&psla[24];
    if ( v22 )
      CBreakArray::ReplaceBreak(v22, v6, a3, a4);
    v23 = v47;
    if ( *v47 )
      CBreakArray::ReplaceBreak(*v47, v6, a3, a4);
    v24 = (unsigned __int8 *)lpMem;
    v25 = *(_QWORD *)(*(_QWORD *)lpMem + 16LL);
    v47 = **(CBreakArray ****)lpMem;
    v26 = (SCRIPT_LOGATTR **)*((_QWORD *)lpMem + 1);
    v50 = v25;
    psla = *v26;
    v27 = 0;
    v43 = 0;
    if ( v42 <= 0 )
      goto LABEL_54;
    do
    {
      v28 = v27;
      v29 = (const SCRIPT_ANALYSIS *)(v25 + 8LL * v27);
      v30 = CUniscribe::GeteProp(Uniscribe, *(_WORD *)&v29[1] & 0x3FF);
      if ( (*(_DWORD *)v30 & 0x20000) != 0 && (*(_DWORD *)v30 & 0xC0000) != 0 )
      {
        if ( ScriptBreak(
               (const WCHAR *)v47 + *(int *)(v25 + 8 * v28),
               *(_DWORD *)(v25 + 8 * v28 + 8) - *(_DWORD *)(v25 + 8 * v28),
               v29 + 1,
               psla) )
        {
          break;
        }
        v32 = *(_DWORD *)(v25 + 8 * v28);
        v33 = v32 + v8;
        v34 = (unsigned int)(*(_DWORD *)(v25 + 8 * v28 + 8) + ~v32);
        if ( (int)v34 >= 0 )
        {
          v35 = psla;
          v36 = v33;
          do
          {
            v37 = *(CBreakArray **)&v21[24];
            if ( v37 )
            {
              v38 = (*(_BYTE *)&v35[v34] >> 3) & 1;
              v44 = v36 + v34;
              CBreakArray::SetBreak(v37, v36 + v34, v38);
              v39 = v44;
            }
            else
            {
              v39 = v36 + v34;
            }
            if ( *v23 )
            {
              LOBYTE(v31) = ~*(_BYTE *)&v35[v34];
              CBreakArray::SetBreak(*v23, v39, (v31 >> 2) & 1);
            }
            v34 = (unsigned int)(v34 - 1);
          }
          while ( (int)v34 >= 0 );
          v8 = v46;
          v25 = v50;
        }
      }
      else
      {
        v40 = *(CBreakArray **)&v21[24];
        v41 = (_DWORD *)(v25 + 8 * v28);
        if ( v40 )
          CBreakArray::ClearBreak(v40, *v41 + v8, *(_DWORD *)(v25 + 8 * v28 + 8) - *v41);
        if ( *v23 )
          CBreakArray::ClearBreak(*v23, v8 + *v41, *(_DWORD *)(v25 + 8 * (v28 + 1)) - *v41);
      }
      v27 = v43 + 1;
      v43 = v27;
    }
    while ( v27 < v42 );
  }
  v24 = (unsigned __int8 *)lpMem;
LABEL_54:
  if ( v24 && v53 != v24 )
    CW32System::FreePv(v24);
}

```

## disassembly

```asm
0x18008b030  push    rbp
0x18008b032  push    rbx
0x18008b033  push    rsi
0x18008b034  push    rdi
0x18008b035  push    r12
0x18008b037  push    r13
0x18008b039  push    r14
0x18008b03b  push    r15
0x18008b03d  lea     rbp, [rsp-1C8h]
0x18008b045  sub     rsp, 2C8h
0x18008b04c  mov     rax, cs:__security_cookie
0x18008b053  xor     rax, rsp
0x18008b056  mov     [rbp+200h+var_50], rax
0x18008b05d  xor     ebx, ebx
0x18008b05f  mov     [rsp+300h+var_2A8], edx
0x18008b063  mov     [rsp+300h+psla], rcx
0x18008b068  mov     r12d, r9d
0x18008b06b  mov     esi, r8d
0x18008b06e  mov     edi, edx
0x18008b070  mov     r13, rcx
0x18008b073  test    r8d, r8d
0x18008b076  jnz     short loc_18008B081
0x18008b078  test    r9d, r9d
0x18008b07b  jz      loc_18008B421
0x18008b081  mov     rdx, [rcx+10h]; struct CTxtEdit *
0x18008b085  mov     r8d, edi; int
0x18008b088  lea     rcx, [rbp+200h+var_270]; this
0x18008b08c  call    ??0CTxtPtr@@QEAA@PEAVCTxtEdit@@J@Z; CTxtPtr::CTxtPtr(CTxtEdit *,long)
0x18008b091  test    edi, edi
0x18008b093  jle     short loc_18008B0A0
0x18008b095  lea     r15d, [rdi-1]
0x18008b099  mov     [rsp+300h+var_298], r15d
0x18008b09e  jmp     short loc_18008B0A7
0x18008b0a0  mov     r15d, ebx
0x18008b0a3  mov     [rsp+300h+var_298], ebx
0x18008b0a7  lea     r9, [rsp+300h+var_2AC]; int *
0x18008b0ac  mov     dword ptr [rsp+300h+lpMem], ebx
0x18008b0b0  lea     r8, [rsp+300h+lpMem]; int *
0x18008b0b5  mov     [rsp+300h+var_2AC], ebx
0x18008b0b9  mov     edx, r12d; int
0x18008b0bc  mov     dword ptr [rsp+300h+pwcInChars], ebx; unsigned int
0x18008b0c0  lea     rcx, [rbp+200h+var_270]; this
0x18008b0c4  call    ?FindWhiteSpaceBound@CTxtPtr@@QEAAJJAEAJ0K@Z; CTxtPtr::FindWhiteSpaceBound(long,long &,long &,ulong)
0x18008b0c9  mov     rax, [r13+18h]
0x18008b0cd  mov     ebx, 1
0x18008b0d2  mov     [rbp+200h+var_280], rax
0x18008b0d6  test    rax, rax
0x18008b0d9  jz      short loc_18008B0F4
0x18008b0db  add     r13, 20h ; ' '
0x18008b0df  mov     [rsp+300h+var_2B0], ebx
0x18008b0e3  lea     r11d, [rbx+2]
0x18008b0e7  mov     [rsp+300h+var_290], r13
0x18008b0ec  mov     r13d, r11d
0x18008b0ef  mov     r14, rax
0x18008b0f2  jmp     short loc_18008B113
0x18008b0f4  lea     rax, [r13+20h]
0x18008b0f8  mov     r13d, ebx
0x18008b0fb  mov     r14, [rax]
0x18008b0fe  mov     [rsp+300h+var_290], rax
0x18008b103  test    r14, r14
0x18008b106  jz      short loc_18008B13D
0x18008b108  mov     r11d, ebx
0x18008b10b  mov     [rsp+300h+var_2B0], 0
0x18008b113  cmp     r15d, dword ptr [rsp+300h+lpMem]
0x18008b118  jle     short loc_18008B149
0x18008b11a  mov     edx, r15d; int
0x18008b11d  mov     rcx, r14; this
0x18008b120  call    ?GetBreak@CBreakArray@@QEAAHJ@Z; CBreakArray::GetBreak(long)
0x18008b125  cmp     eax, [rsp+300h+var_2B0]
0x18008b129  jnz     short loc_18008B133
0x18008b12b  test    r11d, r11d
0x18008b12e  jz      short loc_18008B149
0x18008b130  sub     r11d, ebx
0x18008b133  sub     r15d, ebx
0x18008b136  mov     [rsp+300h+var_298], r15d
0x18008b13b  jmp     short loc_18008B113
0x18008b13d  mov     [rsp+300h+var_290], rax
0x18008b142  xor     r14d, r14d
0x18008b145  mov     [rsp+300h+var_2B0], ebx
0x18008b149  mov     edx, r15d
0x18008b14c  lea     rcx, [rbp+200h+var_270]; this
0x18008b150  sub     edx, [rbp+200h+var_260]; int
0x18008b153  call    ?AdvanceCp@CTxtPtr@@QEAAJJ@Z; CTxtPtr::AdvanceCp(long)
0x18008b158  mov     eax, esi
0x18008b15a  lea     r11d, [rsi+rdi]
0x18008b15e  sub     eax, r12d
0x18008b161  add     [rsp+300h+var_2AC], eax
0x18008b165  test    r14, r14
0x18008b168  jz      short loc_18008B195
0x18008b16a  mov     edi, [rsp+300h+var_2AC]
0x18008b16e  cmp     r11d, edi
0x18008b171  jge     short loc_18008B191
0x18008b173  mov     edx, r11d; int
0x18008b176  mov     rcx, r14; this
0x18008b179  call    ?GetBreak@CBreakArray@@QEAAHJ@Z; CBreakArray::GetBreak(long)
0x18008b17e  cmp     eax, [rsp+300h+var_2B0]
0x18008b182  jnz     short loc_18008B18C
0x18008b184  test    r13d, r13d
0x18008b187  jz      short loc_18008B191
0x18008b189  sub     r13d, ebx
0x18008b18c  add     r11d, ebx
0x18008b18f  jmp     short loc_18008B16E
0x18008b191  mov     edi, [rsp+300h+var_2A8]
0x18008b195  mov     r14d, r12d
0x18008b198  sub     r14d, esi
0x18008b19b  add     r14d, r11d
0x18008b19e  cmp     r15d, r14d
0x18008b1a1  jnz     short loc_18008B1DD
0x18008b1a3  mov     rcx, [rbp+200h+var_280]; this
0x18008b1a7  test    rcx, rcx
0x18008b1aa  jz      short loc_18008B1B9
0x18008b1ac  xor     r9d, r9d; int
0x18008b1af  mov     r8d, esi; int
0x18008b1b2  mov     edx, edi; int
0x18008b1b4  call    ?ReplaceBreak@CBreakArray@@QEAAJJJJ@Z; CBreakArray::ReplaceBreak(long,long,long)
0x18008b1b9  mov     r14, [rsp+300h+psla]
0x18008b1be  mov     rcx, [r14+20h]; this
0x18008b1c2  test    rcx, rcx
0x18008b1c5  jz      loc_18008B421
0x18008b1cb  xor     r9d, r9d; int
0x18008b1ce  mov     r8d, esi; int
0x18008b1d1  mov     edx, edi; int
0x18008b1d3  call    ?ReplaceBreak@CBreakArray@@QEAAJJJJ@Z; CBreakArray::ReplaceBreak(long,long,long)
0x18008b1d8  jmp     loc_18008B421
0x18008b1dd  xor     r13d, r13d
0x18008b1e0  mov     [rsp+300h+lpMem], r13
0x18008b1e5  mov     [rsp+300h+var_2B0], r13d
0x18008b1ea  call    ?GetUniscribe@@YAPEAVCUniscribe@@XZ; GetUniscribe(void)
0x18008b1ef  mov     [rbp+200h+var_280], rax
0x18008b1f3  test    rax, rax
0x18008b1f6  jz      loc_18008B421
0x18008b1fc  sub     r14d, r15d
0x18008b1ff  mov     [rsp+300h+var_2D8], 7; unsigned int
0x18008b207  lea     r9, [rsp+300h+lpMem]; struct tagUSP_CLIENT **
0x18008b20c  mov     dword ptr [rsp+300h+pwcInChars], r14d; int
0x18008b211  lea     rdx, [rbp+200h+var_250]; unsigned __int8 *
0x18008b215  call    ?CreateClientStruc@CUniscribe@@QEAAHPEAEJPEAPEAUtagUSP_CLIENT@@JK@Z; CUniscribe::CreateClientStruc(uchar *,long,tagUSP_CLIENT * *,long,ulong)
0x18008b21a  mov     r8, [rsp+300h+lpMem]
0x18008b21f  test    r8, r8
0x18008b222  jz      loc_18008B421
0x18008b228  mov     r8, [r8]
0x18008b22b  lea     rcx, [rbp+200h+var_270]; this
0x18008b22f  mov     edx, r14d; int
0x18008b232  mov     r8, [r8]; unsigned __int16 *
0x18008b235  call    ?GetText@CTxtPtr@@QEAAJJPEAG@Z; CTxtPtr::GetText(long,ushort *)
0x18008b23a  mov     rdx, [rsp+300h+lpMem]; struct tagUSP_CLIENT *
0x18008b23f  lea     r9, [rsp+300h+var_2B0]; int *
0x18008b244  mov     [rsp+300h+var_2C0], r13d; int
0x18008b249  xor     r8d, r8d; unsigned __int16
0x18008b24c  mov     [rsp+300h+var_2C8], r13w; unsigned __int16
0x18008b252  mov     [rsp+300h+var_2D0], r13d; int
0x18008b257  mov     rcx, [rdx]; this
0x18008b25a  mov     [rsp+300h+var_2D8], r14d; cInChars
0x18008b25f  mov     rax, [rcx]
0x18008b262  mov     [rsp+300h+pwcInChars], rax; pwcInChars
0x18008b267  call    ?ItemizeString@CUniscribe@@QEAAHPEAUtagUSP_CLIENT@@GPEAHPEAGHHGH@Z; CUniscribe::ItemizeString(tagUSP_CLIENT *,ushort,int *,ushort *,int,int,ushort,int)
0x18008b26c  test    eax, eax
0x18008b26e  jle     loc_18008B409
0x18008b274  mov     r14, [rsp+300h+psla]
0x18008b279  mov     rcx, [r14+18h]; this
0x18008b27d  test    rcx, rcx
0x18008b280  jz      short loc_18008B28F
0x18008b282  mov     r9d, r12d; int
0x18008b285  mov     r8d, esi; int
0x18008b288  mov     edx, edi; int
0x18008b28a  call    ?ReplaceBreak@CBreakArray@@QEAAJJJJ@Z; CBreakArray::ReplaceBreak(long,long,long)
0x18008b28f  mov     r13, [rsp+300h+var_290]
0x18008b294  mov     rcx, [r13+0]; this
0x18008b298  test    rcx, rcx
0x18008b29b  jz      short loc_18008B2AA
0x18008b29d  mov     r9d, r12d; int
0x18008b2a0  mov     r8d, esi; int
0x18008b2a3  mov     edx, edi; int
0x18008b2a5  call    ?ReplaceBreak@CBreakArray@@QEAAJJJJ@Z; CBreakArray::ReplaceBreak(long,long,long)
0x18008b2aa  mov     rcx, [rsp+300h+lpMem]
0x18008b2af  mov     rax, [rcx]
0x18008b2b2  mov     r12, [rax+10h]
0x18008b2b6  mov     rax, [rax]
0x18008b2b9  mov     [rsp+300h+var_290], rax
0x18008b2be  mov     rax, [rcx+8]
0x18008b2c2  mov     [rbp+200h+var_278], r12
0x18008b2c6  mov     rax, [rax]
0x18008b2c9  mov     [rsp+300h+psla], rax
0x18008b2ce  xor     eax, eax
0x18008b2d0  mov     [rsp+300h+var_2AC], eax
0x18008b2d4  cmp     [rsp+300h+var_2B0], eax
0x18008b2d8  jle     loc_18008B40E
0x18008b2de  mov     rcx, [rbp+200h+var_280]; this
0x18008b2e2  movsxd  rsi, eax
0x18008b2e5  mov     eax, 3FFh
0x18008b2ea  lea     rdi, [r12+rsi*8]
0x18008b2ee  movzx   edx, word ptr [rdi+4]
0x18008b2f2  and     dx, ax; unsigned __int16
0x18008b2f5  call    ?GeteProp@CUniscribe@@QEAAPEBUSCRIPT_PROPERTIES@@G@Z; CUniscribe::GeteProp(ushort)
0x18008b2fa  test    dword ptr [rax], 20000h
0x18008b300  jz      loc_18008B3B5
0x18008b306  test    dword ptr [rax], 0C0000h
0x18008b30c  jz      loc_18008B3B5
0x18008b312  movsxd  rax, dword ptr [r12+rsi*8]
0x18008b316  lea     r8, [rdi+4]; psa
0x18008b31a  mov     edx, [r12+rsi*8+8]
0x18008b31f  mov     rcx, [rsp+300h+var_290]
0x18008b324  sub     edx, [r12+rsi*8]; cChars
0x18008b328  mov     r9, [rsp+300h+psla]; psla
0x18008b32d  lea     rcx, [rcx+rax*2]; pwcChars
0x18008b331  call    cs:__imp_ScriptBreak
0x18008b337  test    eax, eax
0x18008b339  jnz     loc_18008B409
0x18008b33f  mov     edi, [r12+rsi*8]
0x18008b343  lea     eax, [rdi+r15]
0x18008b347  not     edi
0x18008b349  add     edi, [r12+rsi*8+8]
0x18008b34e  js      loc_18008B3F5
0x18008b354  mov     r15, [rsp+300h+psla]
0x18008b359  mov     r12d, eax
0x18008b35c  mov     rcx, [r14+18h]; this
0x18008b360  test    rcx, rcx
0x18008b363  jz      short loc_18008B384
0x18008b365  movzx   r8d, byte ptr [rdi+r15]
0x18008b36a  lea     edx, [r12+rdi]; int
0x18008b36e  shr     r8d, 3
0x18008b372  and     r8d, ebx; int
0x18008b375  mov     [rsp+300h+var_2A8], edx
0x18008b379  call    ?SetBreak@CBreakArray@@QEAAXJH@Z; CBreakArray::SetBreak(long,int)
0x18008b37e  mov     eax, [rsp+300h+var_2A8]
0x18008b382  jmp     short loc_18008B388
0x18008b384  lea     eax, [r12+rdi]
0x18008b388  mov     rcx, [r13+0]; this
0x18008b38c  test    rcx, rcx
0x18008b38f  jz      short loc_18008B3A6
0x18008b391  mov     r8b, [rdi+r15]
0x18008b395  mov     edx, eax; int
0x18008b397  not     r8b
0x18008b39a  shr     r8d, 2
0x18008b39e  and     r8d, ebx; int
0x18008b3a1  call    ?SetBreak@CBreakArray@@QEAAXJH@Z; CBreakArray::SetBreak(long,int)
0x18008b3a6  sub     edi, ebx
0x18008b3a8  jns     short loc_18008B35C
0x18008b3aa  mov     r15d, [rsp+300h+var_298]
0x18008b3af  mov     r12, [rbp+200h+var_278]
0x18008b3b3  jmp     short loc_18008B3F5
0x18008b3b5  mov     rcx, [r14+18h]; this
0x18008b3b9  lea     rdi, [r12+rsi*8]
0x18008b3bd  test    rcx, rcx
0x18008b3c0  jz      short loc_18008B3D5
0x18008b3c2  mov     eax, [rdi]
0x18008b3c4  mov     r8d, [r12+rsi*8+8]
0x18008b3c9  sub     r8d, eax; int
0x18008b3cc  lea     edx, [rax+r15]; int
0x18008b3d0  call    ?ClearBreak@CBreakArray@@QEAAXJJ@Z; CBreakArray::ClearBreak(long,long)
0x18008b3d5  mov     rcx, [r13+0]; this
0x18008b3d9  mov     rax, rbx
0x18008b3dc  test    rcx, rcx
0x18008b3df  jz      short loc_18008B3F5
0x18008b3e1  mov     edx, [rdi]
0x18008b3e3  add     rax, rsi
0x18008b3e6  mov     r8d, [r12+rax*8]
0x18008b3ea  sub     r8d, edx; int
0x18008b3ed  add     edx, r15d; int
0x18008b3f0  call    ?ClearBreak@CBreakArray@@QEAAXJJ@Z; CBreakArray::ClearBreak(long,long)
0x18008b3f5  mov     eax, [rsp+300h+var_2AC]
0x18008b3f9  add     eax, ebx
0x18008b3fb  mov     [rsp+300h+var_2AC], eax
0x18008b3ff  cmp     eax, [rsp+300h+var_2B0]
0x18008b403  jl      loc_18008B2DE
0x18008b409  mov     rcx, [rsp+300h+lpMem]; lpMem
0x18008b40e  test    rcx, rcx
0x18008b411  jz      short loc_18008B421
0x18008b413  lea     rax, [rbp+200h+var_250]
0x18008b417  cmp     rax, rcx
0x18008b41a  jz      short loc_18008B421
0x18008b41c  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x18008b421  mov     rcx, [rbp+200h+var_50]
0x18008b428  xor     rcx, rsp; StackCookie
0x18008b42b  call    __security_check_cookie
0x18008b430  add     rsp, 2C8h
0x18008b437  pop     r15
0x18008b439  pop     r14
0x18008b43b  pop     r13
0x18008b43d  pop     r12
0x18008b43f  pop     rdi
0x18008b440  pop     rsi
0x18008b441  pop     rbx
0x18008b442  pop     rbp
0x18008b443  retn
```
