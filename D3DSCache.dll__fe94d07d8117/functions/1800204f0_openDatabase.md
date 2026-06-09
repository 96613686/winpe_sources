# openDatabase

- ea: `0x1800204f0`
- end: `0x180020b6f`
- name: `openDatabase`
- size: `1663`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `33`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800434e0`
- `0x1800966a0`
- `0x1800966c0`
- `0x1800967b0`

## callees

- `0x180012470`
- `0x180020330`
- `0x180020410`
- `0x1800204f0`
- `0x180020b78`
- `0x180020d70`
- `0x180033188`
- `0x180034900`
- `0x1800366bc`
- `0x180036770`
- `0x180037858`
- `0x1800379c8`
- `0x180037f9c`
- `0x18003a860`
- `0x18003b5b4`
- `0x18003ce8c`
- `0x1800419a0`
- `0x180042500`
- `0x180045374`
- `0x1800572fc`
- `0x18005a564`
- `0x18005b800`
- `0x18007888c`
- `0x18007edf0`
- `0x180085760`
- `0x180086758`
- `0x18008821c`
- `0x18008a884`
- `0x18008ae20`
- `0x18008b600`
- `0x180096850`
- `0x180099300`
- `0x1800a8010`

## pseudocode

```c
__int64 __fastcall openDatabase(const char *a1, _QWORD *a2, int a3, const char *a4)
{
  __int64 v4; // r14
  __int64 v5; // r15
  __int64 result; // rax
  int v9; // r12d
  unsigned int v10; // edi
  _QWORD *v11; // rax
  _QWORD *v12; // rbx
  unsigned int v13; // ebp
  _QWORD *v14; // rax
  __int64 v15; // rax
  int v16; // eax
  _BYTE *v17; // r12
  unsigned int v18; // eax
  unsigned int v19; // r12d
  const char *v20; // r8
  unsigned int v21; // eax
  __int64 v22; // rdi
  __int64 v23; // rdi
  bool v24; // zf
  unsigned int v25; // eax
  int v26; // edi
  _QWORD *i; // rdi
  void (__fastcall *v28)(_QWORD); // rax
  __int64 v29; // rax
  __int64 v30; // [rsp+20h] [rbp-78h]
  _BYTE *v31; // [rsp+30h] [rbp-68h]
  __int64 v32; // [rsp+38h] [rbp-60h] BYREF
  __int64 v33; // [rsp+40h] [rbp-58h] BYREF
  _DWORD *v34; // [rsp+48h] [rbp-50h]
  __int64 *v36; // [rsp+A8h] [rbp+10h]
  unsigned int v37; // [rsp+B0h] [rbp+18h] BYREF
  const char *v38; // [rsp+B8h] [rbp+20h]

  v38 = a4;
  v4 = 0;
  v5 = 0;
  v32 = 0;
  v33 = 0;
  if ( !a2 )
    return sqlite3ReportError(21, 183032, "misuse");
  *a2 = 0;
  result = sqlite3_initialize();
  if ( !(_DWORD)result )
  {
    if ( (_BYTE)word_1800C6974 )
    {
      if ( (a3 & 0x8000) != 0 )
      {
        v9 = 0;
      }
      else
      {
        v9 = 1;
        if ( (a3 & 0x10000) == 0 )
          v9 = HIBYTE(word_1800C6974);
      }
    }
    else
    {
      v9 = 0;
    }
    if ( (a3 & 0x40000) != 0 )
    {
      a3 &= ~0x20000u;
    }
    else if ( dword_1800C6ABC )
    {
      a3 |= 0x20000u;
    }
    v10 = a3 & 0xFFF600E7;
    v37 = v10;
    v11 = (_QWORD *)sqlite3Malloc(792);
    v12 = v11;
    v13 = 7;
    if ( !v11 )
      goto LABEL_18;
    memset_0(v11, 0, 0x318u);
    v14 = v12 + 3;
    v36 = v12 + 3;
    if ( v9 )
    {
      v15 = sqlite3MutexAlloc(1);
      *v36 = v15;
      if ( !v15 )
      {
        sqlite3_free(v12);
        v12 = 0;
        goto LABEL_18;
      }
      v14 = v12 + 3;
    }
    else
    {
      v36 = v12 + 3;
    }
    sqlite3_mutex_enter(*v14);
    *((_DWORD *)v12 + 10) = 2;
    *((_BYTE *)v12 + 113) = 109;
    *((_DWORD *)v12 + 104) = 1;
    v16 = -1;
    v34 = v12 + 11;
    if ( (v10 & 0x2000000) == 0 )
      v16 = 255;
    *((_DWORD *)v12 + 22) = v16;
    v12[4] = v12 + 84;
    *((_WORD *)v12 + 210) = 0;
    *(_OWORD *)(v12 + 17) = xmmword_1800B7148;
    *(_OWORD *)(v12 + 19) = xmmword_1800B7158;
    *((_BYTE *)v12 + 101) = 1;
    *((_BYTE *)v12 + 106) = -1;
    *(_OWORD *)(v12 + 21) = xmmword_1800B7168;
    *((_DWORD *)v12 + 45) = 0;
    v12[8] = qword_1800C6A98;
    v12[26] = off_1800C6610;
    v12[6] |= 0xE00480E0uLL;
    *((_DWORD *)v12 + 29) = 0;
    v12[79] = 0;
    v12[78] = 0;
    v12[80] = 0;
    v12[70] = 0;
    v12[69] = 0;
    v12[71] = 0;
    createCollation((__int64)v12, (__int64)"BINARY", 1u, 0, (__int64)&binCollFunc, 0);
    createCollation((__int64)v12, (__int64)"BINARY", 3u, 0, (__int64)&binCollFunc, 0);
    createCollation((__int64)v12, (__int64)"BINARY", 2u, 0, (__int64)&binCollFunc, 0);
    createCollation((__int64)v12, (__int64)"NOCASE", 1u, 0, (__int64)nocaseCollatingFunc, 0);
    createCollation((__int64)v12, (__int64)"RTRIM", 1u, 0, (__int64)rtrimCollFunc, 0);
    v17 = (char *)v12 + 103;
    v31 = (char *)v12 + 103;
    if ( !*((_BYTE *)v12 + 103) )
    {
      *((_DWORD *)v12 + 19) = v10;
      if ( ((1 << (v10 & 7)) & 0x46) != 0 )
      {
        v18 = sqlite3ParseUri(v38, a1, &v37, v12, &v32, &v33);
        v10 = v37;
        v4 = v32;
        v5 = v33;
      }
      else
      {
        v18 = sqlite3ReportError(21, 183247, "misuse");
      }
      v19 = v18;
      if ( v18 )
      {
        if ( v18 == 7 )
          sqlite3OomFault(v12);
        v20 = "%s";
        if ( !v5 )
          v20 = 0;
        sqlite3ErrorWithMsg(v12, v19, v20, v5);
        sqlite3_free(v5);
        v17 = (char *)v12 + 103;
      }
      else
      {
        LODWORD(v30) = 0;
        v21 = sqlite3BtreeOpen(*v12, v4, v12, v12[4] + 8LL, v30, v10 | 0x100);
        if ( v21 )
        {
          if ( v21 == 3082 )
            v21 = 7;
          sqlite3Error(v12, v21);
          v17 = (char *)v12 + 103;
        }
        else
        {
          sqlite3BtreeEnter(*(_QWORD *)(v12[4] + 8LL));
          v22 = v12[4];
          v17 = (char *)v12 + 103;
          *(_QWORD *)(v22 + 24) = sqlite3SchemaGet(v12, *(_QWORD *)(v22 + 8));
          if ( !*v31 )
            sqlite3SetTextEncoding(v12);
          sqlite3BtreeLeave(*(_QWORD *)(v12[4] + 8LL));
          v23 = v12[4];
          *(_QWORD *)(v23 + 56) = sqlite3SchemaGet(v12, 0);
          *(_QWORD *)v12[4] = "main";
          *(_BYTE *)(v12[4] + 16LL) = 3;
          *(_QWORD *)(v12[4] + 32LL) = "temp";
          *(_BYTE *)(v12[4] + 48LL) = 1;
          v24 = *v31 == 0;
          *((_BYTE *)v12 + 113) = 118;
          if ( v24 )
          {
            sqlite3Error(v12, 0);
            if ( (unsigned int)sqlite3_overload_function(v12, "MATCH", 2) == 7 )
              sqlite3OomFault(v12);
            v25 = sqlite3_errcode(v12);
            v26 = 0;
            if ( v25 )
            {
LABEL_47:
              sqlite3Error(v12, v25);
            }
            else
            {
              while ( v26 < 2 )
              {
                v25 = ((__int64 (__fastcall *)(_QWORD *))funcs_1800209CB[v26++])(v12);
                if ( v25 )
                  goto LABEL_47;
              }
              sqlite3AutoLoadExtensions((__int64)v12);
              if ( (unsigned int)sqlite3_errcode(v12) )
                goto LABEL_49;
            }
            setupLookaside(v12, 0, (unsigned int)dword_1800C6984, (unsigned int)dword_1800C6988);
            sqlite3_wal_autocheckpoint(v12, 1000);
          }
        }
      }
    }
LABEL_49:
    sqlite3_mutex_leave(*v36);
    if ( (unsigned int)sqlite3SafetyCheckSickOrOk(v12) )
    {
      if ( *v17 )
        goto LABEL_18;
      v13 = *v34 & v12[10];
    }
    else
    {
      v13 = sqlite3ReportError(21, 182518, "misuse");
    }
    if ( (_BYTE)v13 != 7 )
    {
      if ( v13 )
        *((_BYTE *)v12 + 113) = -70;
      goto LABEL_68;
    }
LABEL_18:
    if ( v12 )
    {
      if ( (unsigned int)sqlite3SafetyCheckSickOrOk(v12) )
      {
        sqlite3_mutex_enter(v12[3]);
        if ( (*((_BYTE *)v12 + 110) & 8) != 0 )
          ((void (__fastcall *)(__int64, _QWORD, _QWORD *, _QWORD))v12[31])(8, v12[32], v12, 0);
        disconnectAllVtab(v12);
        callFinaliser(v12, 136);
        if ( (unsigned int)connectionIsBusy(v12) )
        {
          sqlite3ErrorWithMsg(v12, 5, "unable to close due to unfinalized statements or unfinished backups");
          sqlite3_mutex_leave(v12[3]);
        }
        else
        {
          for ( i = (_QWORD *)v12[98]; i; i = (_QWORD *)v12[98] )
          {
            v12[98] = *i;
            v28 = (void (__fastcall *)(_QWORD))i[2];
            if ( v28 )
              v28(i[1]);
            sqlite3_free(i);
          }
          *((_BYTE *)v12 + 113) = -89;
          sqlite3LeaveMutexAndCloseZombie(v12);
        }
      }
      else
      {
        sqlite3ReportError(21, 181033, "misuse");
      }
    }
    v12 = 0;
LABEL_68:
    *a2 = v12;
    if ( v4 )
    {
      v29 = databaseName(v4);
      sqlite3_free(v29 - 4);
    }
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x1800204f0  mov     [rsp+arg_18], r9
0x1800204f5  mov     [rsp+arg_0], rcx
0x1800204fa  push    rsi
0x1800204fb  push    rdi
0x1800204fc  push    r14
0x1800204fe  push    r15
0x180020500  sub     rsp, 78h
0x180020504  xor     r14d, r14d
0x180020507  xor     r15d, r15d
0x18002050a  mov     [rsp+98h+var_60], r14
0x18002050f  mov     edi, r8d
0x180020512  mov     [rsp+98h+var_58], r15
0x180020517  mov     rsi, rdx
0x18002051a  test    rdx, rdx
0x18002051d  jnz     short loc_18002053A
0x18002051f  lea     r8, aMisuse; "misuse"
0x180020526  mov     edx, 2CAF8h
0x18002052b  mov     ecx, 15h
0x180020530  call    sqlite3ReportError
0x180020535  jmp     loc_180020B64
0x18002053a  mov     [rdx], r14
0x18002053d  call    sqlite3_initialize
0x180020542  test    eax, eax
0x180020544  jnz     loc_180020B64
0x18002054a  cmp     byte ptr cs:word_1800C6974, r14b
0x180020551  mov     [rsp+98h+var_28], rbx
0x180020556  mov     [rsp+98h+var_30], rbp
0x18002055b  mov     [rsp+98h+var_38], r12
0x180020560  mov     [rsp+98h+var_40], r13
0x180020565  mov     r13d, 1
0x18002056b  jnz     short loc_180020572
0x18002056d  xor     r12d, r12d
0x180020570  jmp     short loc_18002058E
0x180020572  bt      edi, 0Fh
0x180020576  jnb     short loc_18002057D
0x180020578  xor     r12d, r12d
0x18002057b  jmp     short loc_18002058E
0x18002057d  mov     r12d, r13d
0x180020580  bt      edi, 10h
0x180020584  jb      short loc_18002058E
0x180020586  movzx   r12d, byte ptr cs:word_1800C6974+1
0x18002058e  bt      edi, 12h
0x180020592  jnb     short loc_18002059A
0x180020594  btr     edi, 11h
0x180020598  jmp     short loc_1800205A7
0x18002059a  cmp     cs:dword_1800C6ABC, r14d
0x1800205a1  jz      short loc_1800205A7
0x1800205a3  bts     edi, 11h
0x1800205a7  and     edi, 0FFF600E7h
0x1800205ad  mov     ecx, 318h
0x1800205b2  mov     [rsp+98h+arg_10], edi
0x1800205b9  call    sqlite3Malloc
0x1800205be  mov     rbx, rax
0x1800205c1  mov     ebp, 7
0x1800205c6  test    rax, rax
0x1800205c9  jz      short loc_18002060E
0x1800205cb  xor     edx, edx; Val
0x1800205cd  mov     r8d, 318h; Size
0x1800205d3  mov     rcx, rax; void *
0x1800205d6  call    memset_0
0x1800205db  lea     rax, [rbx+18h]
0x1800205df  mov     [rsp+98h+arg_8], rax
0x1800205e7  test    r12d, r12d
0x1800205ea  jz      short loc_180020647
0x1800205ec  mov     ecx, r13d
0x1800205ef  call    sqlite3MutexAlloc
0x1800205f4  mov     rcx, [rsp+98h+arg_8]
0x1800205fc  mov     [rcx], rax
0x1800205ff  test    rax, rax
0x180020602  jnz     short loc_180020642
0x180020604  mov     rcx, rbx
0x180020607  call    sqlite3_free
0x18002060c  xor     ebx, ebx
0x18002060e  test    rbx, rbx
0x180020611  jz      loc_180020B33
0x180020617  mov     rcx, rbx
0x18002061a  call    sqlite3SafetyCheckSickOrOk
0x18002061f  test    eax, eax
0x180020621  jnz     loc_180020A7E
0x180020627  lea     r8, aMisuse; "misuse"
0x18002062e  mov     edx, 2C329h
0x180020633  mov     ecx, 15h
0x180020638  call    sqlite3ReportError
0x18002063d  jmp     loc_180020B33
0x180020642  mov     rax, rcx
0x180020645  jmp     short loc_18002064F
0x180020647  mov     [rsp+98h+arg_8], rax
0x18002064f  mov     rcx, [rax]
0x180020652  call    sqlite3_mutex_enter
0x180020657  mov     dword ptr [rbx+28h], 2
0x18002065e  lea     rcx, [rbx+58h]
0x180020662  mov     byte ptr [rbx+71h], 6Dh ; 'm'
0x180020666  lea     r12, binCollFunc
0x18002066d  mov     [rbx+1A0h], r13d
0x180020674  mov     eax, 0FFFFFFFFh
0x180020679  mov     edx, 0FFh
0x18002067e  mov     [rsp+98h+var_50], rcx
0x180020683  bt      edi, 19h
0x180020687  mov     [rsp+98h+var_70], r14
0x18002068c  movzx   r8d, r13b
0x180020690  mov     [rsp+98h+var_78], r12
0x180020695  cmovnb  eax, edx
0x180020698  xor     r9d, r9d
0x18002069b  mov     [rcx], eax
0x18002069d  lea     rdx, aBinary_0; "BINARY"
0x1800206a4  lea     rax, [rbx+2A0h]
0x1800206ab  mov     rcx, rbx
0x1800206ae  mov     [rbx+20h], rax
0x1800206b2  xor     eax, eax
0x1800206b4  mov     [rbx+1A4h], ax
0x1800206bb  movups  xmm0, cs:xmmword_1800B7148
0x1800206c2  movups  xmmword ptr [rbx+88h], xmm0
0x1800206c9  movups  xmm1, cs:xmmword_1800B7158
0x1800206d0  movups  xmmword ptr [rbx+98h], xmm1
0x1800206d7  movups  xmm0, cs:xmmword_1800B7168
0x1800206de  mov     [rbx+65h], r13b
0x1800206e2  mov     byte ptr [rbx+6Ah], 0FFh
0x1800206e6  movups  xmmword ptr [rbx+0A8h], xmm0
0x1800206ed  mov     [rbx+0B4h], eax
0x1800206f3  mov     rax, cs:qword_1800C6A98
0x1800206fa  mov     [rbx+40h], rax
0x1800206fe  lea     rax, off_1800C6610; "ANY"
0x180020705  mov     [rbx+0D0h], rax
0x18002070c  mov     eax, 0E00480E0h
0x180020711  or      [rbx+30h], rax
0x180020715  mov     [rbx+74h], r14d
0x180020719  mov     [rbx+278h], r14
0x180020720  mov     [rbx+270h], r14
0x180020727  mov     [rbx+280h], r14
0x18002072e  mov     [rbx+230h], r14
0x180020735  mov     [rbx+228h], r14
0x18002073c  mov     [rbx+238h], r14
0x180020743  call    createCollation
0x180020748  xor     r9d, r9d
0x18002074b  mov     [rsp+98h+var_70], r14
0x180020750  mov     r8b, 3
0x180020753  mov     [rsp+98h+var_78], r12
0x180020758  lea     rdx, aBinary_0; "BINARY"
0x18002075f  mov     rcx, rbx
0x180020762  call    createCollation
0x180020767  xor     r9d, r9d
0x18002076a  mov     [rsp+98h+var_70], r14
0x18002076f  mov     r8b, 2
0x180020772  mov     [rsp+98h+var_78], r12
0x180020777  lea     rdx, aBinary_0; "BINARY"
0x18002077e  mov     rcx, rbx
0x180020781  call    createCollation
0x180020786  lea     rax, nocaseCollatingFunc
0x18002078d  mov     [rsp+98h+var_70], r14
0x180020792  xor     r9d, r9d
0x180020795  mov     [rsp+98h+var_78], rax
0x18002079a  movzx   r8d, r13b
0x18002079e  lea     rdx, aNocase; "NOCASE"
0x1800207a5  mov     rcx, rbx
0x1800207a8  call    createCollation
0x1800207ad  lea     rax, rtrimCollFunc
0x1800207b4  mov     [rsp+98h+var_70], r14
0x1800207b9  xor     r9d, r9d
0x1800207bc  mov     [rsp+98h+var_78], rax
0x1800207c1  movzx   r8d, r13b
0x1800207c5  lea     rdx, aRtrim_0; "RTRIM"
0x1800207cc  mov     rcx, rbx
0x1800207cf  call    createCollation
0x1800207d4  lea     r12, [rbx+67h]
0x1800207d8  mov     [rsp+98h+var_68], r12
0x1800207dd  cmp     [r12], r14b
0x1800207e1  jnz     loc_180020A05
0x1800207e7  mov     ecx, edi
0x1800207e9  mov     [rbx+4Ch], edi
0x1800207ec  and     ecx, ebp
0x1800207ee  shl     r13d, cl
0x1800207f1  test    r13b, 46h
0x1800207f5  jnz     short loc_18002080F
0x1800207f7  lea     r8, aMisuse; "misuse"
0x1800207fe  mov     edx, 2CBCFh
0x180020803  mov     ecx, 15h
0x180020808  call    sqlite3ReportError
0x18002080d  jmp     short loc_180020854
0x18002080f  mov     rdx, [rsp+98h+arg_0]
0x180020817  lea     rax, [rsp+98h+var_58]
0x18002081c  mov     rcx, [rsp+98h+arg_18]
0x180020824  lea     r8, [rsp+98h+arg_10]
0x18002082c  mov     [rsp+98h+var_70], rax
0x180020831  mov     r9, rbx
0x180020834  lea     rax, [rsp+98h+var_60]
0x180020839  mov     [rsp+98h+var_78], rax
0x18002083e  call    sqlite3ParseUri
0x180020843  mov     edi, [rsp+98h+arg_10]
0x18002084a  mov     r14, [rsp+98h+var_60]
0x18002084f  mov     r15, [rsp+98h+var_58]
0x180020854  mov     r12d, eax
0x180020857  test    eax, eax
0x180020859  jz      short loc_180020897
0x18002085b  cmp     eax, ebp
0x18002085d  jnz     short loc_180020867
0x18002085f  mov     rcx, rbx
0x180020862  call    sqlite3OomFault
0x180020867  xor     eax, eax
0x180020869  lea     r8, aS_10; "%s"
0x180020870  test    r15, r15
0x180020873  mov     r9, r15
0x180020876  mov     edx, r12d
0x180020879  mov     rcx, rbx
0x18002087c  cmovz   r8, rax
0x180020880  call    sqlite3ErrorWithMsg
0x180020885  mov     rcx, r15
0x180020888  call    sqlite3_free
0x18002088d  mov     r12, [rsp+98h+var_68]
0x180020892  jmp     loc_180020A05
0x180020897  mov     r9, [rbx+20h]
0x18002089b  bts     edi, 8
0x18002089f  mov     rcx, [rbx]
0x1800208a2  add     r9, 8
0x1800208a6  mov     dword ptr [rsp+98h+var_70], edi
0x1800208aa  mov     r8, rbx
0x1800208ad  mov     rdx, r14
0x1800208b0  mov     dword ptr [rsp+98h+var_78], 0
0x1800208b8  call    sqlite3BtreeOpen
0x1800208bd  test    eax, eax
0x1800208bf  jz      short loc_1800208DD
0x1800208c1  cmp     eax, 0C0Ah
0x1800208c6  mov     rcx, rbx
0x1800208c9  cmovz   eax, ebp
0x1800208cc  mov     edx, eax
0x1800208ce  call    sqlite3Error
0x1800208d3  mov     r12, [rsp+98h+var_68]
0x1800208d8  jmp     loc_180020A05
0x1800208dd  mov     rcx, [rbx+20h]
0x1800208e1  mov     rcx, [rcx+8]
0x1800208e5  call    sqlite3BtreeEnter
0x1800208ea  mov     rdi, [rbx+20h]
0x1800208ee  mov     rcx, rbx
0x1800208f1  mov     rdx, rdi
0x1800208f4  mov     rdx, [rdx+8]
0x1800208f8  call    sqlite3SchemaGet
0x1800208fd  mov     r12, [rsp+98h+var_68]
0x180020902  mov     [rdi+18h], rax
0x180020906  cmp     byte ptr [r12], 0
0x18002090b  jnz     short loc_180020921
0x18002090d  mov     rax, [rbx+20h]
0x180020911  mov     rcx, rbx
0x180020914  mov     rdx, [rax+18h]
0x180020918  movzx   edx, byte ptr [rdx+71h]
0x18002091c  call    sqlite3SetTextEncoding
0x180020921  mov     rcx, [rbx+20h]
0x180020925  mov     rcx, [rcx+8]
0x180020929  call    sqlite3BtreeLeave
0x18002092e  mov     rdi, [rbx+20h]
0x180020932  xor     edx, edx
0x180020934  mov     rcx, rbx
0x180020937  call    sqlite3SchemaGet
0x18002093c  mov     [rdi+38h], rax
0x180020940  lea     rcx, aMain; "main"
0x180020947  mov     rax, [rbx+20h]
0x18002094b  mov     [rax], rcx
0x18002094e  lea     rcx, aTemp; "temp"
0x180020955  mov     rax, [rbx+20h]
0x180020959  mov     byte ptr [rax+10h], 3
0x18002095d  mov     rax, [rbx+20h]
0x180020961  mov     [rax+20h], rcx
0x180020965  mov     rax, [rbx+20h]
0x180020969  mov     byte ptr [rax+30h], 1
0x18002096d  cmp     byte ptr [r12], 0
0x180020972  mov     byte ptr [rbx+71h], 76h ; 'v'
0x180020976  jnz     loc_180020A05
0x18002097c  xor     edx, edx
0x18002097e  mov     rcx, rbx
0x180020981  call    sqlite3Error
0x180020986  mov     r8d, 2
0x18002098c  lea     rdx, aMatch; "MATCH"
0x180020993  mov     rcx, rbx
0x180020996  call    sqlite3_overload_function
0x18002099b  cmp     eax, ebp
0x18002099d  jnz     short loc_1800209A7
0x18002099f  mov     rcx, rbx
0x1800209a2  call    sqlite3OomFault
0x1800209a7  mov     rcx, rbx
0x1800209aa  call    sqlite3_errcode
0x1800209af  xor     edi, edi
0x1800209b1  test    eax, eax
0x1800209b3  jnz     short loc_1800209D6
0x1800209b5  lea     r15, funcs_1800209CB
0x1800209bc  mov     rcx, rbx
0x1800209bf  cmp     edi, 2
0x1800209c2  jge     short loc_180020A3B
0x1800209c4  movsxd  rax, edi
0x1800209c7  mov     rax, ds:(funcs_1800209CB - 1800A9580h)[r15+rax*8]
0x1800209cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209d0  inc     edi
0x1800209d2  test    eax, eax
0x1800209d4  jz      short loc_1800209BC
0x1800209d6  mov     edx, eax
0x1800209d8  mov     rcx, rbx
0x1800209db  call    sqlite3Error
0x1800209e0  mov     r9d, cs:dword_1800C6988
0x1800209e7  xor     edx, edx
0x1800209e9  mov     r8d, cs:dword_1800C6984
0x1800209f0  mov     rcx, rbx
0x1800209f3  call    setupLookaside
0x1800209f8  mov     edx, 3E8h
  ... truncated ...
```
