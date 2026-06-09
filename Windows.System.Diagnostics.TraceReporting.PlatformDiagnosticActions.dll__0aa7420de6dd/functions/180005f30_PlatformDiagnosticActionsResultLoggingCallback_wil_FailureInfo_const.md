# PlatformDiagnosticActionsResultLoggingCallback(wil::FailureInfo const &)

- ea: `0x180005f30`
- end: `0x180006116`
- name: `?PlatformDiagnosticActionsResultLoggingCallback@@YAXAEBUFailureInfo@wil@@@Z`
- size: `486`
- prototype: `void __fastcall(const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000108c`
- `0x1800016a0`
- `0x180005f30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005fa8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005fa8`

## pseudocode

```c
void __fastcall PlatformDiagnosticActionsResultLoggingCallback(const struct wil::FailureInfo *a1)
{
  int v1; // r14d
  __int64 *v3; // rdi
  const unsigned __int16 *v4; // rsi
  const unsigned __int16 *v5; // rbx
  DWORD CurrentThreadId; // eax
  const unsigned __int16 *v7; // rdx
  int v8; // r8d
  __int64 v9; // rax
  __int64 v10; // rcx
  int v11; // ecx
  __int64 v12; // rcx
  int v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[32]; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v19; // [rsp+70h] [rbp-90h]
  int v20; // [rsp+78h] [rbp-88h]
  int v21; // [rsp+7Ch] [rbp-84h]
  int *v22; // [rsp+80h] [rbp-80h]
  __int64 v23; // [rsp+88h] [rbp-78h]
  char *v24; // [rsp+90h] [rbp-70h]
  __int64 v25; // [rsp+98h] [rbp-68h]
  __int64 *v26; // [rsp+A0h] [rbp-60h]
  __int64 v27; // [rsp+A8h] [rbp-58h]
  char *v28; // [rsp+B0h] [rbp-50h]
  __int64 v29; // [rsp+B8h] [rbp-48h]
  __int64 *v30; // [rsp+C0h] [rbp-40h]
  __int64 v31; // [rsp+C8h] [rbp-38h]
  __int64 *v32; // [rsp+D0h] [rbp-30h]
  int v33; // [rsp+D8h] [rbp-28h]
  int v34; // [rsp+DCh] [rbp-24h]
  const unsigned __int16 *v35; // [rsp+E0h] [rbp-20h]
  int v36; // [rsp+E8h] [rbp-18h]
  int v37; // [rsp+ECh] [rbp-14h]
  const unsigned __int16 *v38; // [rsp+F0h] [rbp-10h]
  int v39; // [rsp+F8h] [rbp-8h]
  int v40; // [rsp+FCh] [rbp-4h]

  v1 = 2;
  if ( (unsigned int)dword_180015000 > 2 )
  {
    LODWORD(v15) = *((_DWORD *)a1 + 2);
    v3 = &qword_180010778;
    v4 = &byte_18000F937;
    v5 = &byte_18000F937;
    if ( *((_QWORD *)a1 + 6) )
      v4 = (const unsigned __int16 *)*((_QWORD *)a1 + 6);
    if ( *((_QWORD *)a1 + 5) )
      v5 = (const unsigned __int16 *)*((_QWORD *)a1 + 5);
    if ( *((_QWORD *)a1 + 3) )
      v3 = (__int64 *)*((_QWORD *)a1 + 3);
    CurrentThreadId = GetCurrentThreadId();
    v7 = (const unsigned __int16 *)*((_QWORD *)a1 + 7);
    v8 = 1;
    HIDWORD(v15) = CurrentThreadId;
    LODWORD(v16) = *((_DWORD *)a1 + 17);
    HIDWORD(v16) = *(_DWORD *)a1;
    v17 = *((_DWORD *)a1 + 16);
    v9 = -1;
    if ( v4 )
    {
      v10 = -1;
      do
        ++v10;
      while ( *((_BYTE *)v4 + v10) );
      v11 = v10 + 1;
    }
    else
    {
      v4 = &byte_18000F937;
      v11 = 1;
    }
    v38 = v4;
    v39 = v11;
    v40 = 0;
    if ( v5 )
    {
      v12 = -1;
      do
        ++v12;
      while ( *((_BYTE *)v5 + v12) );
      v13 = v12 + 1;
    }
    else
    {
      v5 = &byte_18000F937;
      v13 = 1;
    }
    v35 = v5;
    v36 = v13;
    v37 = 0;
    if ( v3 )
    {
      v14 = -1;
      do
        ++v14;
      while ( *((_WORD *)v3 + v14) );
      v1 = 2 * v14 + 2;
    }
    else
    {
      v3 = &qword_180010778;
    }
    v32 = v3;
    v30 = &v15;
    v28 = (char *)&v15 + 4;
    v26 = &v16;
    v24 = (char *)&v16 + 4;
    v22 = &v17;
    v33 = v1;
    v34 = 0;
    v31 = 4;
    v29 = 4;
    v27 = 4;
    v25 = 4;
    v23 = 4;
    if ( v7 )
    {
      do
        ++v9;
      while ( *((_BYTE *)v7 + v9) );
      v8 = v9 + 1;
    }
    else
    {
      v7 = &byte_18000F937;
    }
    v19 = v7;
    v20 = v8;
    v21 = 0;
    tlgWriteTransfer_EventWriteTransfer(&dword_180015000, byte_180011E83, 0, 0, 11, v18, v15, v16, v17);
  }
}

```

## disassembly

```asm
0x180005f30  push    rbp
0x180005f32  push    rbx
0x180005f33  push    rsi
0x180005f34  push    rdi
0x180005f35  push    r12
0x180005f37  push    r13
0x180005f39  push    r14
0x180005f3b  push    r15
0x180005f3d  lea     rbp, [rsp-18h]
0x180005f42  sub     rsp, 118h
0x180005f49  mov     rax, cs:__security_cookie
0x180005f50  xor     rax, rsp
0x180005f53  mov     [rbp+50h+var_50], rax
0x180005f57  mov     eax, cs:dword_180015000
0x180005f5d  mov     r14d, 2
0x180005f63  mov     r15, rcx
0x180005f66  cmp     eax, r14d
0x180005f69  jbe     loc_1800060F6
0x180005f6f  mov     eax, [rcx+8]
0x180005f72  lea     r13, byte_18000F937
0x180005f79  xor     r12d, r12d
0x180005f7c  mov     [rsp+150h+var_120], eax
0x180005f80  cmp     [rcx+30h], r12
0x180005f84  lea     rdi, qword_180010778
0x180005f8b  mov     rsi, r13
0x180005f8e  mov     rbx, r13
0x180005f91  cmovnz  rsi, [rcx+30h]
0x180005f96  cmp     [rcx+28h], r12
0x180005f9a  cmovnz  rbx, [rcx+28h]
0x180005f9f  cmp     [rcx+18h], r12
0x180005fa3  cmovnz  rdi, [rcx+18h]
0x180005fa8  call    cs:__imp_GetCurrentThreadId
0x180005fae  mov     rdx, [r15+38h]
0x180005fb2  lea     r8d, [r14-1]
0x180005fb6  mov     [rsp+150h+var_11C], eax
0x180005fba  mov     eax, [r15+44h]
0x180005fbe  mov     [rsp+150h+var_118], eax
0x180005fc2  mov     eax, [r15]
0x180005fc5  mov     [rsp+150h+var_114], eax
0x180005fc9  mov     eax, [r15+40h]
0x180005fcd  mov     [rsp+150h+var_110], eax
0x180005fd1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005fd5  test    rsi, rsi
0x180005fd8  jz      short loc_180005FEA
0x180005fda  mov     rcx, rax
0x180005fdd  inc     rcx
0x180005fe0  cmp     [rsi+rcx], r12b
0x180005fe4  jnz     short loc_180005FDD
0x180005fe6  inc     ecx
0x180005fe8  jmp     short loc_180005FF0
0x180005fea  mov     rsi, r13
0x180005fed  mov     ecx, r8d
0x180005ff0  mov     [rbp+50h+var_60], rsi
0x180005ff4  mov     [rbp+50h+var_58], ecx
0x180005ff7  mov     [rbp+50h+var_54], r12d
0x180005ffb  test    rbx, rbx
0x180005ffe  jz      short loc_180006010
0x180006000  mov     rcx, rax
0x180006003  inc     rcx
0x180006006  cmp     [rbx+rcx], r12b
0x18000600a  jnz     short loc_180006003
0x18000600c  inc     ecx
0x18000600e  jmp     short loc_180006016
0x180006010  mov     rbx, r13
0x180006013  mov     ecx, r8d
0x180006016  mov     [rbp+50h+var_70], rbx
0x18000601a  mov     [rbp+50h+var_68], ecx
0x18000601d  mov     [rbp+50h+var_64], r12d
0x180006021  test    rdi, rdi
0x180006024  jz      short loc_18000603D
0x180006026  mov     rcx, rax
0x180006029  inc     rcx
0x18000602c  cmp     [rdi+rcx*2], r12w
0x180006031  jnz     short loc_180006029
0x180006033  lea     r14d, ds:2[rcx*2]
0x18000603b  jmp     short loc_180006044
0x18000603d  lea     rdi, qword_180010778
0x180006044  mov     [rbp+50h+var_80], rdi
0x180006048  lea     rcx, [rsp+150h+var_120]
0x18000604d  mov     [rbp+50h+var_90], rcx
0x180006051  lea     rcx, [rsp+150h+var_11C]
0x180006056  mov     [rbp+50h+var_A0], rcx
0x18000605a  lea     rcx, [rsp+150h+var_118]
0x18000605f  mov     [rbp+50h+var_B0], rcx
0x180006063  lea     rcx, [rsp+150h+var_114]
0x180006068  mov     [rbp+50h+var_C0], rcx
0x18000606c  lea     rcx, [rsp+150h+var_110]
0x180006071  mov     [rbp+50h+var_D0], rcx
0x180006075  mov     [rbp+50h+var_78], r14d
0x180006079  mov     [rbp+50h+var_74], r12d
0x18000607d  mov     [rbp+50h+var_88], 4
0x180006085  mov     [rbp+50h+var_98], 4
0x18000608d  mov     [rbp+50h+var_A8], 4
0x180006095  mov     [rbp+50h+var_B8], 4
0x18000609d  mov     [rbp+50h+var_C8], 4
0x1800060a5  test    rdx, rdx
0x1800060a8  jz      short loc_1800060B9
0x1800060aa  inc     rax
0x1800060ad  cmp     [rdx+rax], r12b
0x1800060b1  jnz     short loc_1800060AA
0x1800060b3  lea     r8d, [rax+1]
0x1800060b7  jmp     short loc_1800060BC
0x1800060b9  mov     rdx, r13
0x1800060bc  lea     rax, [rsp+150h+var_100]
0x1800060c1  mov     [rsp+150h+var_E0], rdx
0x1800060c6  mov     [rsp+150h+var_D8], r8d
0x1800060cb  lea     rdx, byte_180011E83
0x1800060d2  mov     [rsp+150h+var_128], rax
0x1800060d7  lea     rcx, dword_180015000
0x1800060de  xor     r9d, r9d
0x1800060e1  mov     [rsp+150h+var_130], 0Bh
0x1800060e9  xor     r8d, r8d
0x1800060ec  mov     [rsp+150h+var_D4], r12d
0x1800060f1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800060f6  mov     rcx, [rbp+50h+var_50]
0x1800060fa  xor     rcx, rsp; StackCookie
0x1800060fd  call    __security_check_cookie
0x180006102  add     rsp, 118h
0x180006109  pop     r15
0x18000610b  pop     r14
0x18000610d  pop     r13
0x18000610f  pop     r12
0x180006111  pop     rdi
0x180006112  pop     rsi
0x180006113  pop     rbx
0x180006114  pop     rbp
0x180006115  retn
```
