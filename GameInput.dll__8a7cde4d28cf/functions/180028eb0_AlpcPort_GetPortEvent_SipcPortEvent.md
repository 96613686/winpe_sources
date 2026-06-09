# AlpcPort::GetPortEvent(SipcPortEvent *)

- ea: `0x180028eb0`
- end: `0x1800293ff`
- name: `?GetPortEvent@AlpcPort@@UEAAJPEAUSipcPortEvent@@@Z`
- size: `1359`
- prototype: `__int64 __fastcall(AlpcPort *__hidden this, struct SipcPortEvent *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting`

## callees

- `0x180025d0c`
- `0x180025e24`
- `0x1800281c0`
- `0x180028c10`
- `0x180028eb0`
- `0x180029a2c`
- `0x18002abe0`
- `0x18002afe8`
- `0x18002b108`
- `0x18002bbd0`
- `0x18004c88d`
- `0x18004c8a5`
- `0x18004c8e0`

## import_xrefs

- `ntdll!NtAlpcCancelMessage` at `0x180028fd2`
- `ntdll!NtAlpcCancelMessage` at `0x1800290a4`
- `ntdll!NtAlpcCancelMessage` at `0x180028fd2`
- `ntdll!NtAlpcCancelMessage` at `0x1800290a4`
- `ntdll!NtAlpcDeleteSectionView` at `0x18002929f`
- `ntdll!NtAlpcDeleteSectionView` at `0x1800292ed`
- `ntdll!NtAlpcDeleteSectionView` at `0x18002929f`
- `ntdll!NtAlpcDeleteSectionView` at `0x1800292ed`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180028f51`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800291a6`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180028f51`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x1800291a6`

## pseudocode

```c
__int64 __fastcall AlpcPort::GetPortEvent(AlpcPort *this, struct SipcPortEvent *a2)
{
  __int16 *v2; // r15
  char *v3; // r12
  _QWORD *v5; // r13
  __int64 v7; // rbx
  __int64 i; // rcx
  int v9; // eax
  __int16 v10; // dx
  signed int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  __int64 v15; // rcx
  unsigned __int64 v16; // rdi
  size_t v17; // rbx
  struct SipcSection *Section; // rax
  unsigned int v19; // edx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  __int64 v23; // rcx
  unsigned __int64 v25; // rdi
  size_t v26; // rbx
  __int64 v27; // rcx
  int v28; // eax
  int v29; // eax
  unsigned int v30; // ebx
  unsigned __int64 v31; // rdi
  size_t v32; // rbx
  void *v33; // rbx
  void *v34; // r12
  unsigned __int64 v35; // r15
  unsigned __int64 v36; // r8
  int v37; // edi
  int v38; // eax
  int v39; // eax
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  int v42; // eax
  __int64 v43; // rcx
  struct SipcSection *v44; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v45; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v47; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v48; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v49; // [rsp+70h] [rbp-90h]
  _BYTE v50[4]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v51; // [rsp+84h] [rbp-7Ch]
  __int128 v52; // [rsp+94h] [rbp-6Ch]
  __int64 v53; // [rsp+A8h] [rbp-58h]
  char v54[68]; // [rsp+C0h] [rbp-40h] BYREF
  char v55[76]; // [rsp+104h] [rbp+4h] BYREF

  v2 = (__int16 *)((char *)this + 56);
  v3 = (char *)this + 424;
  *(_OWORD *)((char *)this + 56) = 0;
  v5 = (_QWORD *)((char *)this + 424);
  *(_OWORD *)((char *)this + 72) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 53) = 0;
  v7 = 0;
  *((_WORD *)this + 29) = 40;
  *((_DWORD *)this + 106) = 1610612736;
  for ( i = *((_QWORD *)this + 6); ; i = *((_QWORD *)this + 6) )
  {
    v46 = 368;
    v45 = 0;
    v9 = NtAlpcSendWaitReceivePort(i, 0, 0, 0, v2, &v46, v5, &v45);
    if ( v9 )
    {
      *(_DWORD *)a2 = 0;
      if ( v9 == 258 || v9 == -1073741823 || !*((_QWORD *)this + 6) )
        return 1;
      else
        return v9 | 0x90000000;
    }
    v10 = *((_WORD *)this + 30);
    v11 = v10 & 0xFFFF00FF;
    if ( v11 <= 7 )
      break;
    v20 = v11 - 8;
    if ( !v20 )
      goto LABEL_23;
    v21 = v20 - 1;
    if ( !v21 )
      goto LABEL_23;
    v22 = v21 - 1;
    if ( !v22 )
    {
      memset_0(v54, 0, sizeof(v54));
      memset_0(v55, 0, 0x44u);
      v25 = *v2;
      if ( *v2 < 0 )
        v25 = 0;
      v26 = 200;
      if ( v25 < 0xC8 )
        v26 = v25;
      memcpy_0(v50, v2 + 20, v26);
      memset_0(&v50[v26], 0, 200 - v26);
      if ( v25 == 200 && v50[0] == 2 )
      {
        v40 = v51;
        *(_DWORD *)a2 = 2;
        v41 = v52;
        *(_OWORD *)((char *)a2 + 8) = v40;
        *(_OWORD *)((char *)a2 + 24) = v41;
        *((_DWORD *)a2 + 10) = *((_DWORD *)this + 16);
        *((_DWORD *)a2 + 11) = *((_DWORD *)this + 18);
        *((_QWORD *)a2 + 6) = v53;
        *((_BYTE *)a2 + 56) = v50[2];
        *((_BYTE *)a2 + 57) = v50[3];
        return 0;
      }
      AlpcPort::RejectClientConnection(this);
LABEL_33:
      v7 = 0;
      goto LABEL_34;
    }
    if ( v22 != 2 )
      goto LABEL_23;
LABEL_34:
    *(_OWORD *)v2 = 0;
    *((_OWORD *)v2 + 1) = 0;
    *((_QWORD *)v2 + 4) = 0;
    *v5 = 0;
    *((_WORD *)this + 29) = 40;
    *(_DWORD *)v5 = 1610612736;
  }
  if ( v11 == 7 )
    goto LABEL_23;
  v12 = v11 - 1;
  if ( !v12 )
    goto LABEL_23;
  v13 = v12 - 1;
  if ( !v13 )
    goto LABEL_23;
  v14 = v13 - 1;
  if ( !v14 )
  {
    if ( (*((_DWORD *)this + 107) & 0x40000000) != 0 )
    {
      v27 = *((_QWORD *)this + 6);
      v2[2] &= ~0x2000u;
      v44 = 0;
      v28 = NtAlpcSendWaitReceivePort(v27, 0, v2, v3, 0, 0, 0, &v44);
      if ( v28 >= 0 )
      {
        v31 = *v2;
        if ( *v2 < 0 )
          v31 = 0;
        v47 = 0;
        v32 = 8;
        if ( v31 < 8 )
          v32 = v31;
        memcpy_0(&v47, v2 + 20, v32);
        memset_0((char *)&v47 + v32, 0, 8 - v32);
        if ( v31 == 8 )
        {
          *((_DWORD *)this + 107) &= ~0x40000000u;
          v33 = (void *)*((_QWORD *)this + 6);
          v34 = (void *)*((_QWORD *)this + 56);
          v35 = v47;
          v36 = *((_QWORD *)this + 57);
          v44 = 0;
          v48 = 0;
          v49 = 0;
          v37 = AlpcSection::Attach(this, v34, v36, v33, v47, (struct SipcSectionId *)&v48, &v44);
          if ( v37 >= 0 )
          {
            SipcPort::AddReceivedSection(this, v44, a2);
            return 0;
          }
          v38 = AlpcSection::SendXvmmDisconnect(v35);
          if ( v38 < 0 )
          {
            SipcFailFast((unsigned int)v38);
            __debugbreak();
          }
          AlpcSection::SendAlpcDisconnect(v33, (const struct SipcSectionId *)&v48);
          v39 = NtAlpcDeleteSectionView(v33, 0, v34);
          if ( v39 < 0 )
          {
            v42 = v39 | 0x10000000;
            v43 = 2147549183LL;
            if ( v42 < 0 )
              v43 = (unsigned int)v42;
            SipcFailFast(v43);
            JUMPOUT(0x1800293FELL);
          }
          return (unsigned int)v37;
        }
        v30 = -2147024809;
      }
      else
      {
        v29 = v28 | 0x10000000;
        v30 = -2147418113;
        if ( v29 < 0 )
          v30 = v29;
      }
      if ( (*((_DWORD *)this + 107) & 0x40000000) != 0
        && (int)NtAlpcDeleteSectionView(*((_QWORD *)this + 6), 0, *((_QWORD *)this + 56)) >= 0 )
      {
        *((_DWORD *)this + 107) &= ~0x40000000u;
      }
      *(_DWORD *)a2 = 0;
      return v30;
    }
    if ( (v10 & 0x2000) != 0 )
    {
      v15 = *((_QWORD *)this + 6);
      *((_WORD *)this + 30) = v10 & 0xDFFF;
      NtAlpcCancelMessage(v15, 0, (char *)this + 464, 0x2000);
    }
    v16 = *v2;
    if ( *v2 < 0 )
      v16 = 0;
    v17 = 32;
    v48 = 0;
    if ( v16 < 0x20 )
      v17 = v16;
    v49 = 0;
    memcpy_0(&v48, v2 + 20, v17);
    memset_0((char *)&v48 + v17, 0, 32 - v17);
    if ( v16 != 32 )
      goto LABEL_33;
    Section = SipcPort::FindSection(this, (const struct SipcSectionId *)&v48);
    v7 = 0;
    if ( Section )
    {
      if ( *((_DWORD *)Section + 22) == 1 )
      {
        *((_DWORD *)Section + 22) = 2;
        SipcPort::IncreaseSectionEventCount(this, v19);
      }
    }
    goto LABEL_34;
  }
  if ( (unsigned int)(v14 - 1) <= 1 )
  {
    if ( (*((_DWORD *)this + 107) & 0x20000000) == 0 )
      goto LABEL_59;
    v7 = *((_QWORD *)this + 58);
    if ( v7 == *((_QWORD *)this + 6) )
    {
      v7 = 0;
      goto LABEL_59;
    }
    if ( !v7 )
LABEL_59:
      AlpcPort::Disconnect(this);
    *(_DWORD *)a2 = 3;
    *((_QWORD *)a2 + 1) = v7;
    return 0;
  }
LABEL_23:
  if ( (v10 & 0x2000) != 0 )
  {
    v23 = *((_QWORD *)this + 6);
    *((_WORD *)this + 30) = v10 & 0xDFFF;
    NtAlpcCancelMessage(v23, 0, (char *)this + 464, 0x2000);
  }
  *(_DWORD *)a2 = 1;
  *((_DWORD *)a2 + 2) = *((__int16 *)this + 30) & 0xFFFF00FF;
  return 2147549183LL;
}

```

## disassembly

```asm
0x180028eb0  mov     [rsp-8+arg_10], rbx
0x180028eb5  push    rbp
0x180028eb6  push    rsi
0x180028eb7  push    rdi
0x180028eb8  push    r12
0x180028eba  push    r13
0x180028ebc  push    r14
0x180028ebe  push    r15
0x180028ec0  lea     rbp, [rsp-60h]
0x180028ec5  sub     rsp, 160h
0x180028ecc  mov     rax, cs:__security_cookie
0x180028ed3  xor     rax, rsp
0x180028ed6  mov     [rbp+90h+var_40], rax
0x180028eda  lea     r15, [rcx+38h]
0x180028ede  xor     eax, eax
0x180028ee0  xorps   xmm0, xmm0
0x180028ee3  lea     r12, [r15+170h]
0x180028eea  movups  xmmword ptr [r15], xmm0
0x180028eee  mov     rsi, rcx
0x180028ef1  lea     r13, [rcx+1A8h]
0x180028ef8  movups  xmmword ptr [r15+10h], xmm0
0x180028efd  mov     [r15+20h], rax
0x180028f01  mov     r14, rdx
0x180028f04  mov     [r12], rax
0x180028f08  xor     ebx, ebx
0x180028f0a  mov     word ptr [r15+2], 28h ; '('
0x180028f11  mov     dword ptr [r12], 60000000h
0x180028f19  mov     rcx, [rcx+30h]
0x180028f1d  lea     rax, [rsp+190h+var_148]
0x180028f22  mov     [rsp+190h+var_140], 170h
0x180028f2b  mov     [rsp+190h+var_158], rax
0x180028f30  xor     r9d, r9d
0x180028f33  lea     rax, [rsp+190h+var_140]
0x180028f38  mov     [rsp+190h+var_160], r13
0x180028f3d  mov     [rsp+190h+var_168], rax
0x180028f42  xor     r8d, r8d
0x180028f45  xor     edx, edx
0x180028f47  mov     [rsp+190h+var_170], r15
0x180028f4c  mov     [rsp+190h+var_148], rbx
0x180028f51  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180028f58  nop     dword ptr [rax+rax+00h]
0x180028f5d  test    eax, eax
0x180028f5f  jnz     loc_180029399
0x180028f65  movsx   edx, word ptr [rsi+3Ch]
0x180028f69  mov     r8d, 0FFFFDFFFh
0x180028f6f  mov     ecx, edx
0x180028f71  mov     r9d, 2000h
0x180028f77  and     ecx, 0FFFF00FFh
0x180028f7d  cmp     ecx, 7
0x180028f80  jg      loc_18002906C
0x180028f86  jz      loc_180029089
0x180028f8c  sub     ecx, 1
0x180028f8f  jz      loc_180029089
0x180028f95  sub     ecx, 1
0x180028f98  jz      loc_180029089
0x180028f9e  sub     ecx, 1
0x180028fa1  jnz     loc_180029313
0x180028fa7  test    dword ptr [rsi+1ACh], 40000000h
0x180028fb1  jnz     loc_180029177
0x180028fb7  test    r9w, dx
0x180028fbb  jz      short loc_180028FDE
0x180028fbd  mov     rcx, [rsi+30h]
0x180028fc1  and     dx, r8w
0x180028fc5  mov     [rsi+3Ch], dx
0x180028fc9  lea     r8, [rsi+1D0h]
0x180028fd0  xor     edx, edx
0x180028fd2  call    cs:__imp_NtAlpcCancelMessage
0x180028fd9  nop     dword ptr [rax+rax+00h]
0x180028fde  cmp     [r15], bx
0x180028fe2  lea     rdx, [r15+28h]; Src
0x180028fe6  movsx   rdi, word ptr [r15]
0x180028fea  lea     rcx, [rsp+190h+var_130]; void *
0x180028fef  cmovl   rdi, rbx
0x180028ff3  xorps   xmm0, xmm0
0x180028ff6  mov     ebx, 20h ; ' '
0x180028ffb  cmp     rdi, rbx
0x180028ffe  movups  [rsp+190h+var_130], xmm0
0x180029003  cmovb   rbx, rdi
0x180029007  mov     r8, rbx; Size
0x18002900a  movups  [rsp+190h+var_120], xmm0
0x18002900f  call    memcpy_0
0x180029014  mov     r8d, 20h ; ' '
0x18002901a  lea     rcx, [rsp+190h+var_130]
0x18002901f  sub     r8, rbx; Size
0x180029022  add     rcx, rbx; void *
0x180029025  xor     edx, edx; Val
0x180029027  call    memset_0
0x18002902c  cmp     rdi, 20h ; ' '
0x180029030  jnz     loc_180029148
0x180029036  lea     rdx, [rsp+190h+var_130]; struct SipcSectionId *
0x18002903b  mov     rcx, rsi; this
0x18002903e  call    ?FindSection@SipcPort@@IEAAPEAVSipcSection@@AEBVSipcSectionId@@@Z; SipcPort::FindSection(SipcSectionId const &)
0x180029043  xor     ebx, ebx
0x180029045  test    rax, rax
0x180029048  jz      loc_18002914A
0x18002904e  cmp     dword ptr [rax+58h], 1
0x180029052  jnz     loc_18002914A
0x180029058  mov     rcx, rsi; this
0x18002905b  mov     dword ptr [rax+58h], 2
0x180029062  call    ?IncreaseSectionEventCount@SipcPort@@AEAAXI@Z; SipcPort::IncreaseSectionEventCount(uint)
0x180029067  jmp     loc_18002914A
0x18002906c  sub     ecx, 8
0x18002906f  jz      short loc_180029089
0x180029071  sub     ecx, 1
0x180029074  jz      short loc_180029089
0x180029076  sub     ecx, 1
0x180029079  jz      short loc_1800290CE
0x18002907b  sub     ecx, 1
0x18002907e  jz      short loc_180029089
0x180029080  cmp     ecx, 1
0x180029083  jz      loc_18002914A
0x180029089  test    r9w, dx
0x18002908d  jz      short loc_1800290B0
0x18002908f  mov     rcx, [rsi+30h]
0x180029093  and     dx, r8w
0x180029097  mov     [rsi+3Ch], dx
0x18002909b  lea     r8, [rsi+1D0h]
0x1800290a2  xor     edx, edx
0x1800290a4  call    cs:__imp_NtAlpcCancelMessage
0x1800290ab  nop     dword ptr [rax+rax+00h]
0x1800290b0  mov     dword ptr [r14], 1
0x1800290b7  movsx   eax, word ptr [rsi+3Ch]
0x1800290bb  and     eax, 0FFFF00FFh
0x1800290c0  mov     [r14+8], eax
0x1800290c4  mov     eax, 8000FFFFh
0x1800290c9  jmp     loc_1800293BC
0x1800290ce  xor     edx, edx; Val
0x1800290d0  lea     rcx, [rbp+90h+var_D0]; void *
0x1800290d4  lea     r8d, [rdx+44h]; Size
0x1800290d8  call    memset_0
0x1800290dd  xor     edx, edx; Val
0x1800290df  lea     rcx, [rbp+90h+var_8C]; void *
0x1800290e3  lea     r8d, [rdx+44h]; Size
0x1800290e7  call    memset_0
0x1800290ec  cmp     [r15], bx
0x1800290f0  lea     rdx, [r15+28h]; Src
0x1800290f4  movsx   rdi, word ptr [r15]
0x1800290f8  lea     rcx, [rbp+90h+var_110]; void *
0x1800290fc  cmovl   rdi, rbx
0x180029100  mov     eax, 0C8h
0x180029105  cmp     rdi, rax
0x180029108  mov     ebx, eax
0x18002910a  cmovb   rbx, rdi
0x18002910e  mov     r8, rbx; Size
0x180029111  call    memcpy_0
0x180029116  mov     r8d, 0C8h
0x18002911c  lea     rcx, [rbp+90h+var_110]
0x180029120  sub     r8, rbx; Size
0x180029123  add     rcx, rbx; void *
0x180029126  xor     edx, edx; Val
0x180029128  call    memset_0
0x18002912d  cmp     rdi, 0C8h
0x180029134  jnz     short loc_180029140
0x180029136  cmp     [rbp+90h+var_110], 2
0x18002913a  jz      loc_180029358
0x180029140  mov     rcx, rsi; this
0x180029143  call    ?RejectClientConnection@AlpcPort@@UEAAJXZ; AlpcPort::RejectClientConnection(void)
0x180029148  xor     ebx, ebx
0x18002914a  xorps   xmm0, xmm0
0x18002914d  xor     eax, eax
0x18002914f  movups  xmmword ptr [r15], xmm0
0x180029153  movups  xmmword ptr [r15+10h], xmm0
0x180029158  mov     [r15+20h], rax
0x18002915c  mov     [r13+0], rax
0x180029160  mov     word ptr [rsi+3Ah], 28h ; '('
0x180029166  mov     dword ptr [r13+0], 60000000h
0x18002916e  mov     rcx, [rsi+30h]
0x180029172  jmp     loc_180028F1D
0x180029177  mov     rcx, [rsi+30h]
0x18002917b  lea     rax, [rsp+190h+var_150]
0x180029180  and     [r15+4], r8w
0x180029185  mov     r9, r12
0x180029188  mov     [rsp+190h+var_158], rax
0x18002918d  mov     r8, r15
0x180029190  mov     [rsp+190h+var_160], rbx
0x180029195  xor     edx, edx
0x180029197  mov     [rsp+190h+var_168], rbx
0x18002919c  mov     [rsp+190h+var_170], rbx
0x1800291a1  mov     [rsp+190h+var_150], rbx
0x1800291a6  call    cs:__imp_NtAlpcSendWaitReceivePort
0x1800291ad  nop     dword ptr [rax+rax+00h]
0x1800291b2  test    eax, eax
0x1800291b4  jns     short loc_1800291C8
0x1800291b6  or      eax, 10000000h
0x1800291bb  mov     ebx, 8000FFFFh
0x1800291c0  cmovl   ebx, eax
0x1800291c3  jmp     loc_1800292D4
0x1800291c8  cmp     [r15], bx
0x1800291cc  lea     rdx, [r15+28h]; Src
0x1800291d0  movsx   rdi, word ptr [r15]
0x1800291d4  lea     rcx, [rsp+190h+var_138]; void *
0x1800291d9  cmovl   rdi, rbx
0x1800291dd  mov     [rsp+190h+var_138], rbx
0x1800291e2  mov     r12d, 8
0x1800291e8  cmp     rdi, r12
0x1800291eb  mov     ebx, r12d
0x1800291ee  cmovb   rbx, rdi
0x1800291f2  mov     r8, rbx; Size
0x1800291f5  call    memcpy_0
0x1800291fa  mov     r8d, r12d
0x1800291fd  lea     rcx, [rsp+190h+var_138]
0x180029202  sub     r8, rbx; Size
0x180029205  add     rcx, rbx; void *
0x180029208  xor     edx, edx; Val
0x18002920a  call    memset_0
0x18002920f  cmp     rdi, r12
0x180029212  jnz     loc_1800292CF
0x180029218  btr     dword ptr [rsi+1ACh], 1Eh
0x180029220  lea     rax, [rsp+190h+var_150]
0x180029225  mov     rbx, [rsi+30h]
0x180029229  xorps   xmm0, xmm0
0x18002922c  mov     r12, [rsi+1C0h]
0x180029233  mov     r9, rbx; void *
0x180029236  mov     r15, [rsp+190h+var_138]
0x18002923b  mov     rdx, r12; void *
0x18002923e  mov     r8, [rsi+1C8h]; unsigned __int64
0x180029245  mov     rcx, rsi; struct AlpcPort *
0x180029248  mov     [rsp+190h+var_160], rax; struct AlpcSection **
0x18002924d  lea     rax, [rsp+190h+var_130]
0x180029252  mov     [rsp+190h+var_168], rax; struct SipcSectionId *
0x180029257  mov     [rsp+190h+var_170], r15; unsigned __int64
0x18002925c  mov     [rsp+190h+var_150], 0
0x180029265  movups  [rsp+190h+var_130], xmm0
0x18002926a  movups  [rsp+190h+var_120], xmm0
0x18002926f  call    ?Attach@AlpcSection@@CAJPEBVAlpcPort@@PEAX_K12AEAVSipcSectionId@@PEAPEAV1@@Z; AlpcSection::Attach(AlpcPort const *,void *,unsigned __int64,void *,unsigned __int64,SipcSectionId &,AlpcSection * *)
0x180029274  mov     edi, eax
0x180029276  test    eax, eax
0x180029278  jns     short loc_1800292BA
0x18002927a  mov     rcx, r15; unsigned __int64
0x18002927d  call    ?SendXvmmDisconnect@AlpcSection@@CAJ_K@Z; AlpcSection::SendXvmmDisconnect(unsigned __int64)
0x180029282  test    eax, eax
0x180029284  js      loc_1800293E4
0x18002928a  lea     rdx, [rsp+190h+var_130]; struct SipcSectionId *
0x18002928f  mov     rcx, rbx; void *
0x180029292  call    ?SendAlpcDisconnect@AlpcSection@@CAJPEAXAEBVSipcSectionId@@@Z; AlpcSection::SendAlpcDisconnect(void *,SipcSectionId const &)
0x180029297  mov     r8, r12
0x18002929a  xor     edx, edx
0x18002929c  mov     rcx, rbx
0x18002929f  call    cs:__imp_NtAlpcDeleteSectionView
0x1800292a6  nop     dword ptr [rax+rax+00h]
0x1800292ab  test    eax, eax
0x1800292ad  js      loc_1800293EC
0x1800292b3  mov     eax, edi
0x1800292b5  jmp     loc_1800293BC
0x1800292ba  mov     rdx, [rsp+190h+var_150]; struct SipcSection *
0x1800292bf  mov     r8, r14; struct SipcPortEvent *
0x1800292c2  mov     rcx, rsi; this
0x1800292c5  call    ?AddReceivedSection@SipcPort@@IEAAXPEAVSipcSection@@PEAUSipcPortEvent@@@Z; SipcPort::AddReceivedSection(SipcSection *,SipcPortEvent *)
0x1800292ca  jmp     loc_180029395
0x1800292cf  mov     ebx, 80070057h
0x1800292d4  test    dword ptr [rsi+1ACh], 40000000h
0x1800292de  jz      short loc_180029305
0x1800292e0  mov     r8, [rsi+1C0h]
0x1800292e7  xor     edx, edx
0x1800292e9  mov     rcx, [rsi+30h]
0x1800292ed  call    cs:__imp_NtAlpcDeleteSectionView
0x1800292f4  nop     dword ptr [rax+rax+00h]
0x1800292f9  test    eax, eax
0x1800292fb  js      short loc_180029305
0x1800292fd  btr     dword ptr [rsi+1ACh], 1Eh
0x180029305  mov     dword ptr [r14], 0
0x18002930c  mov     eax, ebx
0x18002930e  jmp     loc_1800293BC
0x180029313  sub     ecx, 1
0x180029316  jz      short loc_180029321
0x180029318  cmp     ecx, 1
0x18002931b  jnz     loc_180029089
0x180029321  test    dword ptr [rsi+1ACh], 20000000h
0x18002932b  jz      short loc_180029343
0x18002932d  mov     rbx, [rsi+1D0h]
0x180029334  cmp     rbx, [rsi+30h]
0x180029338  jnz     short loc_18002933E
0x18002933a  xor     ebx, ebx
0x18002933c  jmp     short loc_180029343
0x18002933e  test    rbx, rbx
0x180029341  jnz     short loc_18002934B
0x180029343  mov     rcx, rsi; this
0x180029346  call    ?Disconnect@AlpcPort@@UEAAXXZ; AlpcPort::Disconnect(void)
0x18002934b  mov     dword ptr [r14], 3
0x180029352  mov     [r14+8], rbx
0x180029356  jmp     short loc_180029395
0x180029358  movups  xmm0, [rbp+90h+var_10C]
0x18002935c  mov     dword ptr [r14], 2
0x180029363  movups  xmm1, [rbp+90h+var_FC]
0x180029367  movups  xmmword ptr [r14+8], xmm0
0x18002936c  movups  xmmword ptr [r14+18h], xmm1
0x180029371  mov     eax, [rsi+40h]
0x180029374  mov     [r14+28h], eax
0x180029378  mov     eax, [rsi+48h]
0x18002937b  mov     [r14+2Ch], eax
0x18002937f  mov     rax, [rbp+90h+var_E8]
0x180029383  mov     [r14+30h], rax
0x180029387  mov     al, [rbp+90h+var_10E]
0x18002938a  mov     [r14+38h], al
0x18002938e  mov     al, [rbp+90h+var_10D]
0x180029391  mov     [r14+39h], al
0x180029395  xor     eax, eax
0x180029397  jmp     short loc_1800293BC
0x180029399  mov     [r14], ebx
0x18002939c  cmp     eax, 102h
  ... truncated ...
```
