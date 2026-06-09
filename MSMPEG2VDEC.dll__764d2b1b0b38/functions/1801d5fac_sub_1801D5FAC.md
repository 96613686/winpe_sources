# sub_1801D5FAC

- ea: `0x1801d5fac`
- end: `0x1801d6300`
- name: `sub_1801D5FAC`
- size: `852`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1801d6310`
- `0x1801d79f0`

## callees

- `0x1800c2100`
- `0x1801873e0`
- `0x180189588`
- `0x1801d0980`
- `0x1801d5fac`
- `0x1801f2510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801d625a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801d625a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d6278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d6278`

## string_xrefs

- `0x1801d62cd`: `DX12BufferCopyQueue::Initialize`

## pseudocode

```c
__int64 __fastcall sub_1801D5FAC(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  signed int v6; // edi
  __int64 *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 (__fastcall *v10)(__int64, __int64, __int64 *, _QWORD *); // rdi
  _QWORD *v11; // r14
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 *v16; // rcx
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64, _QWORD, _QWORD, __int64 *, __int64 *); // rbp
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  __int64 (__fastcall *v23)(__int64, _QWORD, _QWORD, __int64 *, __int64 *); // rbp
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 *v28; // rcx
  __int64 (__fastcall *v29)(__int64, __int128 *, __int64 *, __int64 *); // rdi
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 *v40; // rcx
  __int128 v42; // [rsp+40h] [rbp-48h] BYREF

  v42 = 0;
  if ( a2 )
  {
    LODWORD(v42) = 3;
    v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD *))(*(_QWORD *)a2 + 72LL);
    v11 = a1 + 1;
    v12 = a1[1];
    *v11 = 0;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v6 = v10(a2, 3, qword_180226038, v11);
    if ( v6 >= 0 )
    {
      v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, _QWORD, __int64 *, __int64 *))(*(_QWORD *)a2 + 96LL);
      v18 = a1[2];
      a1[2] = 0;
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v6 = v17(a2, 0, 3, *v11, 0, qword_180226400, a1 + 2);
      if ( v6 >= 0 )
      {
        v23 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *, __int64 *))(*(_QWORD *)a2 + 288LL);
        v24 = a1[3];
        a1[3] = 0;
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        v6 = v23(a2, 0, 0, qword_180226018, a1 + 3);
        if ( v6 >= 0 )
        {
          v29 = *(__int64 (__fastcall **)(__int64, __int128 *, __int64 *, __int64 *))(*(_QWORD *)a2 + 64LL);
          v30 = *a1;
          *a1 = 0;
          if ( v30 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          v6 = v29(a2, &v42, qword_1802261C8, a1);
          if ( v6 >= 0 )
          {
            EventW = CreateEventW(0, 0, 0, 0);
            sub_1801D0980(a1 + 5, EventW);
            if ( !a1[5] )
            {
              LastError = GetLastError();
              v6 = LastError;
              if ( LastError > 0 )
                v6 = (unsigned __int16)LastError | 0x80070000;
              if ( v6 < 0 )
              {
                v40 = (__int64 *)qword_180245FF0;
                if ( !qword_180245FF0 )
                {
                  v40 = &qword_180244FA0;
                  qword_180245FF0 = (__int64)&qword_180244FA0;
                }
                if ( *((_BYTE *)v40 + 8) )
                {
                  v8 = sub_1801873E0(v40, v37, v38, v39);
                  if ( *(_DWORD *)(v8 + 1996) != v6 )
                  {
                    v9 = 52;
                    goto LABEL_48;
                  }
                }
              }
            }
          }
          else
          {
            v34 = (__int64 *)qword_180245FF0;
            if ( !qword_180245FF0 )
            {
              v34 = &qword_180244FA0;
              qword_180245FF0 = (__int64)&qword_180244FA0;
            }
            if ( *((_BYTE *)v34 + 8) )
            {
              v8 = sub_1801873E0(v34, v31, v32, v33);
              if ( *(_DWORD *)(v8 + 1996) != v6 )
              {
                v9 = 47;
                goto LABEL_48;
              }
            }
          }
        }
        else
        {
          v28 = (__int64 *)qword_180245FF0;
          if ( !qword_180245FF0 )
          {
            v28 = &qword_180244FA0;
            qword_180245FF0 = (__int64)&qword_180244FA0;
          }
          if ( *((_BYTE *)v28 + 8) )
          {
            v8 = sub_1801873E0(v28, v25, v26, v27);
            if ( *(_DWORD *)(v8 + 1996) != v6 )
            {
              v9 = 46;
              goto LABEL_48;
            }
          }
        }
      }
      else
      {
        v22 = (__int64 *)qword_180245FF0;
        if ( !qword_180245FF0 )
        {
          v22 = &qword_180244FA0;
          qword_180245FF0 = (__int64)&qword_180244FA0;
        }
        if ( *((_BYTE *)v22 + 8) )
        {
          v8 = sub_1801873E0(v22, v19, v20, v21);
          if ( *(_DWORD *)(v8 + 1996) != v6 )
          {
            v9 = 45;
            goto LABEL_48;
          }
        }
      }
    }
    else
    {
      v16 = (__int64 *)qword_180245FF0;
      if ( !qword_180245FF0 )
      {
        v16 = &qword_180244FA0;
        qword_180245FF0 = (__int64)&qword_180244FA0;
      }
      if ( *((_BYTE *)v16 + 8) )
      {
        v8 = sub_1801873E0(v16, v13, v14, v15);
        if ( *(_DWORD *)(v8 + 1996) != v6 )
        {
          v9 = 41;
          goto LABEL_48;
        }
      }
    }
  }
  else
  {
    v6 = -2147024809;
    v7 = (__int64 *)qword_180245FF0;
    if ( !qword_180245FF0 )
    {
      v7 = &qword_180244FA0;
      qword_180245FF0 = (__int64)&qword_180244FA0;
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v8 = sub_1801873E0(v7, 0, a3, a4);
      if ( *(_DWORD *)(v8 + 1996) != -2147024809 )
      {
        v9 = 37;
LABEL_48:
        sub_180189588(v8, "DX12BufferCopyQueue::Initialize", v9, (unsigned int)v6);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801d5fac  mov     [rsp+arg_10], rbx
0x1801d5fb1  push    rbp
0x1801d5fb2  push    rsi
0x1801d5fb3  push    rdi
0x1801d5fb4  push    r14
0x1801d5fb6  push    r15
0x1801d5fb8  sub     rsp, 60h
0x1801d5fbc  mov     rax, cs:__security_cookie
0x1801d5fc3  xor     rax, rsp
0x1801d5fc6  mov     [rsp+88h+var_38], rax
0x1801d5fcb  mov     rbx, rdx
0x1801d5fce  mov     rsi, rcx
0x1801d5fd1  xorps   xmm0, xmm0
0x1801d5fd4  movups  [rsp+88h+var_48], xmm0
0x1801d5fd9  xor     r15d, r15d
0x1801d5fdc  test    rdx, rdx
0x1801d5fdf  jnz     short loc_1801D6026
0x1801d5fe1  mov     edi, 80070057h
0x1801d5fe6  mov     rcx, cs:qword_180245FF0
0x1801d5fed  test    rcx, rcx
0x1801d5ff0  jnz     short loc_1801D6000
0x1801d5ff2  lea     rcx, qword_180244FA0
0x1801d5ff9  mov     cs:qword_180245FF0, rcx
0x1801d6000  cmp     [rcx+8], r15b
0x1801d6004  jz      loc_1801D62DC
0x1801d600a  call    sub_1801873E0
0x1801d600f  cmp     [rax+7CCh], edi
0x1801d6015  jz      loc_1801D62DC
0x1801d601b  mov     r8d, 25h ; '%'
0x1801d6021  jmp     loc_1801D62CA
0x1801d6026  mov     dword ptr [rsp+88h+var_48], 3
0x1801d602e  mov     rax, [rdx]
0x1801d6031  mov     rdi, [rax+48h]
0x1801d6035  lea     r14, [rcx+8]
0x1801d6039  mov     rcx, [r14]
0x1801d603c  mov     [r14], r15
0x1801d603f  test    rcx, rcx
0x1801d6042  jz      short loc_1801D6052
0x1801d6044  mov     rax, [rcx]
0x1801d6047  mov     rax, [rax+10h]
0x1801d604b  call    cs:__guard_dispatch_icall_fptr
0x1801d6051  nop
0x1801d6052  mov     r9, r14
0x1801d6055  lea     r8, qword_180226038
0x1801d605c  mov     edx, 3
0x1801d6061  mov     rcx, rbx
0x1801d6064  mov     rax, rdi
0x1801d6067  call    cs:__guard_dispatch_icall_fptr
0x1801d606d  mov     edi, eax
0x1801d606f  test    eax, eax
0x1801d6071  jns     short loc_1801D60B3
0x1801d6073  mov     rcx, cs:qword_180245FF0
0x1801d607a  test    rcx, rcx
0x1801d607d  jnz     short loc_1801D608D
0x1801d607f  lea     rcx, qword_180244FA0
0x1801d6086  mov     cs:qword_180245FF0, rcx
0x1801d608d  cmp     [rcx+8], r15b
0x1801d6091  jz      loc_1801D62DC
0x1801d6097  call    sub_1801873E0
0x1801d609c  cmp     [rax+7CCh], edi
0x1801d60a2  jz      loc_1801D62DC
0x1801d60a8  mov     r8d, 29h ; ')'
0x1801d60ae  jmp     loc_1801D62CA
0x1801d60b3  mov     rax, [rbx]
0x1801d60b6  mov     rbp, [rax+60h]
0x1801d60ba  lea     rdi, [rsi+10h]
0x1801d60be  mov     rcx, [rdi]
0x1801d60c1  mov     [rdi], r15
0x1801d60c4  test    rcx, rcx
0x1801d60c7  jz      short loc_1801D60D7
0x1801d60c9  mov     rax, [rcx]
0x1801d60cc  mov     rax, [rax+10h]
0x1801d60d0  call    cs:__guard_dispatch_icall_fptr
0x1801d60d6  nop
0x1801d60d7  mov     [rsp+88h+var_58], rdi
0x1801d60dc  lea     rax, qword_180226400
0x1801d60e3  mov     [rsp+88h+var_60], rax
0x1801d60e8  mov     [rsp+88h+var_68], r15
0x1801d60ed  mov     r9, [r14]
0x1801d60f0  xor     edx, edx
0x1801d60f2  lea     r8d, [rdx+3]
0x1801d60f6  mov     rcx, rbx
0x1801d60f9  mov     rax, rbp
0x1801d60fc  call    cs:__guard_dispatch_icall_fptr
0x1801d6102  mov     edi, eax
0x1801d6104  test    eax, eax
0x1801d6106  jns     short loc_1801D6148
0x1801d6108  mov     rcx, cs:qword_180245FF0
0x1801d610f  test    rcx, rcx
0x1801d6112  jnz     short loc_1801D6122
0x1801d6114  lea     rcx, qword_180244FA0
0x1801d611b  mov     cs:qword_180245FF0, rcx
0x1801d6122  cmp     [rcx+8], r15b
0x1801d6126  jz      loc_1801D62DC
0x1801d612c  call    sub_1801873E0
0x1801d6131  cmp     [rax+7CCh], edi
0x1801d6137  jz      loc_1801D62DC
0x1801d613d  mov     r8d, 2Dh ; '-'
0x1801d6143  jmp     loc_1801D62CA
0x1801d6148  mov     rax, [rbx]
0x1801d614b  mov     rbp, [rax+120h]
0x1801d6152  lea     rdi, [rsi+18h]
0x1801d6156  mov     rcx, [rdi]
0x1801d6159  mov     [rdi], r15
0x1801d615c  test    rcx, rcx
0x1801d615f  jz      short loc_1801D616F
0x1801d6161  mov     rax, [rcx]
0x1801d6164  mov     rax, [rax+10h]
0x1801d6168  call    cs:__guard_dispatch_icall_fptr
0x1801d616e  nop
0x1801d616f  mov     [rsp+88h+var_68], rdi
0x1801d6174  lea     r9, qword_180226018
0x1801d617b  xor     r8d, r8d
0x1801d617e  xor     edx, edx
0x1801d6180  mov     rcx, rbx
0x1801d6183  mov     rax, rbp
0x1801d6186  call    cs:__guard_dispatch_icall_fptr
0x1801d618c  mov     edi, eax
0x1801d618e  test    eax, eax
0x1801d6190  jns     short loc_1801D61D2
0x1801d6192  mov     rcx, cs:qword_180245FF0
0x1801d6199  test    rcx, rcx
0x1801d619c  jnz     short loc_1801D61AC
0x1801d619e  lea     rcx, qword_180244FA0
0x1801d61a5  mov     cs:qword_180245FF0, rcx
0x1801d61ac  cmp     [rcx+8], r15b
0x1801d61b0  jz      loc_1801D62DC
0x1801d61b6  call    sub_1801873E0
0x1801d61bb  cmp     [rax+7CCh], edi
0x1801d61c1  jz      loc_1801D62DC
0x1801d61c7  mov     r8d, 2Eh ; '.'
0x1801d61cd  jmp     loc_1801D62CA
0x1801d61d2  mov     rax, [rbx]
0x1801d61d5  mov     rdi, [rax+40h]
0x1801d61d9  mov     rcx, [rsi]
0x1801d61dc  mov     [rsi], r15
0x1801d61df  test    rcx, rcx
0x1801d61e2  jz      short loc_1801D61F2
0x1801d61e4  mov     rdx, [rcx]
0x1801d61e7  mov     rax, [rdx+10h]
0x1801d61eb  call    cs:__guard_dispatch_icall_fptr
0x1801d61f1  nop
0x1801d61f2  mov     r9, rsi
0x1801d61f5  lea     r8, qword_1802261C8
0x1801d61fc  lea     rdx, [rsp+88h+var_48]
0x1801d6201  mov     rcx, rbx
0x1801d6204  mov     rax, rdi
0x1801d6207  call    cs:__guard_dispatch_icall_fptr
0x1801d620d  mov     edi, eax
0x1801d620f  test    eax, eax
0x1801d6211  jns     short loc_1801D6250
0x1801d6213  mov     rcx, cs:qword_180245FF0
0x1801d621a  test    rcx, rcx
0x1801d621d  jnz     short loc_1801D622D
0x1801d621f  lea     rcx, qword_180244FA0
0x1801d6226  mov     cs:qword_180245FF0, rcx
0x1801d622d  cmp     [rcx+8], r15b
0x1801d6231  jz      loc_1801D62DC
0x1801d6237  call    sub_1801873E0
0x1801d623c  cmp     [rax+7CCh], edi
0x1801d6242  jz      loc_1801D62DC
0x1801d6248  mov     r8d, 2Fh ; '/'
0x1801d624e  jmp     short loc_1801D62CA
0x1801d6250  xor     r9d, r9d; lpName
0x1801d6253  xor     r8d, r8d; bInitialState
0x1801d6256  xor     edx, edx; bManualReset
0x1801d6258  xor     ecx, ecx; lpEventAttributes
0x1801d625a  call    cs:CreateEventW
0x1801d6261  nop     dword ptr [rax+rax+00h]
0x1801d6266  mov     rdx, rax
0x1801d6269  lea     rcx, [rsi+28h]
0x1801d626d  call    sub_1801D0980
0x1801d6272  cmp     [rsi+28h], r15
0x1801d6276  jnz     short loc_1801D62DC
0x1801d6278  call    cs:GetLastError
0x1801d627f  nop     dword ptr [rax+rax+00h]
0x1801d6284  mov     edi, eax
0x1801d6286  test    eax, eax
0x1801d6288  jle     short loc_1801D6293
0x1801d628a  movzx   edi, ax
0x1801d628d  or      edi, 80070000h
0x1801d6293  test    edi, edi
0x1801d6295  jns     short loc_1801D62DC
0x1801d6297  mov     rcx, cs:qword_180245FF0
0x1801d629e  test    rcx, rcx
0x1801d62a1  jnz     short loc_1801D62B1
0x1801d62a3  lea     rcx, qword_180244FA0
0x1801d62aa  mov     cs:qword_180245FF0, rcx
0x1801d62b1  cmp     [rcx+8], r15b
0x1801d62b5  jz      short loc_1801D62DC
0x1801d62b7  call    sub_1801873E0
0x1801d62bc  cmp     [rax+7CCh], edi
0x1801d62c2  jz      short loc_1801D62DC
0x1801d62c4  mov     r8d, 34h ; '4'
0x1801d62ca  mov     r9d, edi
0x1801d62cd  lea     rdx, aDx12buffercopy; "DX12BufferCopyQueue::Initialize"
0x1801d62d4  mov     rcx, rax
0x1801d62d7  call    sub_180189588
0x1801d62dc  mov     eax, edi
0x1801d62de  mov     rcx, [rsp+88h+var_38]
0x1801d62e3  xor     rcx, rsp; StackCookie
0x1801d62e6  call    __security_check_cookie
0x1801d62eb  mov     rbx, [rsp+88h+arg_10]
0x1801d62f3  add     rsp, 60h
0x1801d62f7  pop     r15
0x1801d62f9  pop     r14
0x1801d62fb  pop     rdi
0x1801d62fc  pop     rsi
0x1801d62fd  pop     rbp
0x1801d62fe  retn
```
