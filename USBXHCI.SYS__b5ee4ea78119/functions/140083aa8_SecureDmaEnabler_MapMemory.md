# SecureDmaEnabler_MapMemory

- ea: `0x140083aa8`
- end: `0x140083cdb`
- name: `SecureDmaEnabler_MapMemory`
- size: `563`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14008358c`

## callees

- `0x14001ac48`
- `0x14001ad0c`
- `0x14001c178`
- `0x140059970`
- `0x140083aa8`

## import_xrefs

- `ntoskrnl!VslCreateSecureSection` at `0x140083bc2`
- `ntoskrnl!VslCreateSecureSection` at `0x140083bc2`
- `ntoskrnl!VslDeleteSecureSection` at `0x140083b4b`
- `ntoskrnl!VslDeleteSecureSection` at `0x140083b4b`

## pseudocode

```c
__int64 __fastcall SecureDmaEnabler_MapMemory(__int64 a1, _QWORD *a2, int a3, __int64 a4)
{
  bool v4; // zf
  _QWORD *v7; // r8
  int v9; // ebx
  int v10; // eax
  int v11; // edx
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // [rsp+30h] [rbp-39h] BYREF
  __int128 v17; // [rsp+38h] [rbp-31h] BYREF
  __int64 v18; // [rsp+48h] [rbp-21h]
  __int128 v19; // [rsp+50h] [rbp-19h] BYREF
  __int128 v20; // [rsp+60h] [rbp-9h]
  __int128 v21; // [rsp+70h] [rbp+7h]
  __int64 v22; // [rsp+80h] [rbp+17h]

  v4 = *a2 == 0;
  v22 = 0;
  LODWORD(v18) = 0;
  v16 = 0;
  v7 = a2;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v17 = 0;
  if ( v4 )
  {
    v13 = VslCreateSecureSection(&v16, *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1072LL), a2, 4, 1);
    v9 = v13;
    if ( v13 >= 0 )
    {
      v14 = *(_QWORD *)(a1 + 8);
      v22 = 0;
      v15 = *(_QWORD *)(a1 + 16);
      *(_QWORD *)&v21 = 5;
      *(_QWORD *)&v20 = 0;
      *((_QWORD *)&v20 + 1) = v15;
      *((_QWORD *)&v21 + 1) = v16;
      v19 = 0;
      LODWORD(v22) = a3;
      v9 = SecureChannel_SendRequestSynchronously(*(_QWORD *)(v14 + 112), &v19, 56, &v17, 24);
      if ( v9 >= 0 )
      {
        if ( (int)v17 >= 0 )
        {
          *(_DWORD *)(a4 + 12) = 0;
          *(_QWORD *)a4 = *((_QWORD *)&v17 + 1);
          *(_QWORD *)(a4 + 16) = v18;
          *(_QWORD *)(a4 + 24) = v16;
          *(_DWORD *)(a4 + 8) = a3;
          return (unsigned int)v9;
        }
        v9 = v17;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_d(
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
            (_DWORD)a2,
            18,
            14,
            (__int64)WPP_8d19556b374b3e85e4187adf480561f2_Traceguids,
            v17);
        }
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
        (_DWORD)a2,
        18,
        13,
        (__int64)WPP_8d19556b374b3e85e4187adf480561f2_Traceguids,
        v13);
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
        (_DWORD)a2,
        18,
        12,
        (__int64)WPP_8d19556b374b3e85e4187adf480561f2_Traceguids);
    }
    v9 = -1073741637;
  }
  if ( v16 )
  {
    v10 = VslDeleteSecureSection(v16, a2, v7);
    if ( v10 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 3;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
        v11,
        18,
        15,
        (__int64)WPP_8d19556b374b3e85e4187adf480561f2_Traceguids,
        v10);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140083aa8  push    rbp
0x140083aaa  push    rbx
0x140083aab  push    rsi
0x140083aac  push    rdi
0x140083aad  push    r12
0x140083aaf  push    r14
0x140083ab1  lea     rbp, [rsp-2Fh]
0x140083ab6  sub     rsp, 98h
0x140083abd  mov     rax, cs:__security_cookie
0x140083ac4  xor     rax, rsp
0x140083ac7  mov     [rbp+57h+var_38], rax
0x140083acb  xor     eax, eax
0x140083acd  lea     r12, WPP_RECORDER_INITIALIZED
0x140083ad4  cmp     qword ptr [rdx], 0
0x140083ad8  xorps   xmm0, xmm0
0x140083adb  mov     [rbp+57h+var_40], rax
0x140083adf  mov     r14d, r8d
0x140083ae2  mov     dword ptr [rbp+57h+var_78], eax
0x140083ae5  mov     rdi, r9
0x140083ae8  mov     [rbp+57h+var_90], rax
0x140083aec  mov     r8, rdx
0x140083aef  lea     rax, WPP_8d19556b374b3e85e4187adf480561f2_Traceguids
0x140083af6  mov     rsi, rcx
0x140083af9  movups  [rbp+57h+var_70], xmm0
0x140083afd  movups  [rbp+57h+var_60], xmm0
0x140083b01  movups  [rbp+57h+var_50], xmm0
0x140083b05  movups  [rbp+57h+var_88], xmm0
0x140083b09  jz      loc_140083BA5
0x140083b0f  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140083b16  jz      short loc_140083B36
0x140083b18  mov     rcx, [rcx+8]
0x140083b1c  mov     r9d, 0Ch
0x140083b22  mov     dl, 2
0x140083b24  mov     [rsp+0C0h+var_A0], rax
0x140083b29  mov     rcx, [rcx+48h]
0x140083b2d  lea     r8d, [r9+6]
0x140083b31  call    WPP_RECORDER_SF_
0x140083b36  mov     ebx, 0C00000BBh
0x140083b3b  lea     rdi, WPP_8d19556b374b3e85e4187adf480561f2_Traceguids
0x140083b42  mov     rcx, [rbp+57h+var_90]
0x140083b46  test    rcx, rcx
0x140083b49  jz      short loc_140083B86
0x140083b4b  call    cs:__imp_VslDeleteSecureSection
0x140083b52  nop     dword ptr [rax+rax+00h]
0x140083b57  test    eax, eax
0x140083b59  jns     short loc_140083B86
0x140083b5b  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140083b62  jz      short loc_140083B86
0x140083b64  mov     rcx, [rsi+8]
0x140083b68  mov     r9d, 0Fh
0x140083b6e  mov     [rsp+0C0h+var_98], eax
0x140083b72  mov     dl, 3
0x140083b74  mov     [rsp+0C0h+var_A0], rdi
0x140083b79  mov     rcx, [rcx+48h]
0x140083b7d  lea     r8d, [r9+3]
0x140083b81  call    WPP_RECORDER_SF_d
0x140083b86  mov     eax, ebx
0x140083b88  mov     rcx, [rbp+57h+var_38]
0x140083b8c  xor     rcx, rsp; StackCookie
0x140083b8f  call    __security_check_cookie
0x140083b94  add     rsp, 98h
0x140083b9b  pop     r14
0x140083b9d  pop     r12
0x140083b9f  pop     rdi
0x140083ba0  pop     rsi
0x140083ba1  pop     rbx
0x140083ba2  pop     rbp
0x140083ba3  retn
0x140083ba5  mov     rdx, [rcx+8]
0x140083ba9  mov     r9d, 4
0x140083baf  lea     rcx, [rbp+57h+var_90]
0x140083bb3  mov     dword ptr [rsp+0C0h+var_A0], 1
0x140083bbb  mov     rdx, [rdx+430h]
0x140083bc2  call    cs:__imp_VslCreateSecureSection
0x140083bc9  nop     dword ptr [rax+rax+00h]
0x140083bce  mov     ebx, eax
0x140083bd0  test    eax, eax
0x140083bd2  jns     short loc_140083C0F
0x140083bd4  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140083bdb  jz      loc_140083B3B
0x140083be1  mov     rcx, [rsi+8]
0x140083be5  lea     rdi, WPP_8d19556b374b3e85e4187adf480561f2_Traceguids
0x140083bec  mov     r9d, 0Dh
0x140083bf2  mov     [rsp+0C0h+var_98], eax
0x140083bf6  mov     dl, 2
0x140083bf8  mov     [rsp+0C0h+var_A0], rdi
0x140083bfd  mov     rcx, [rcx+48h]
0x140083c01  lea     r8d, [r9+5]
0x140083c05  call    WPP_RECORDER_SF_d
0x140083c0a  jmp     loc_140083B42
0x140083c0f  mov     rcx, [rsi+8]
0x140083c13  lea     r9, [rbp+57h+var_88]
0x140083c17  xor     eax, eax
0x140083c19  mov     dword ptr [rsp+0C0h+var_A0], 18h
0x140083c21  mov     [rbp+57h+var_40], rax
0x140083c25  lea     rdx, [rbp+57h+var_70]
0x140083c29  mov     rax, [rsi+10h]
0x140083c2d  xorps   xmm0, xmm0
0x140083c30  movups  [rbp+57h+var_50], xmm0
0x140083c34  mov     dword ptr [rbp+57h+var_50], 5
0x140083c3b  mov     r8d, 38h ; '8'
0x140083c41  movups  [rbp+57h+var_60], xmm0
0x140083c45  mov     qword ptr [rbp+57h+var_60+8], rax
0x140083c49  mov     rax, [rbp+57h+var_90]
0x140083c4d  mov     qword ptr [rbp+57h+var_50+8], rax
0x140083c51  movups  [rbp+57h+var_70], xmm0
0x140083c55  mov     dword ptr [rbp+57h+var_40], r14d
0x140083c59  mov     rcx, [rcx+70h]
0x140083c5d  call    SecureChannel_SendRequestSynchronously
0x140083c62  mov     ebx, eax
0x140083c64  test    eax, eax
0x140083c66  js      loc_140083B3B
0x140083c6c  mov     eax, dword ptr [rbp+57h+var_88]
0x140083c6f  test    eax, eax
0x140083c71  jns     short loc_140083CB4
0x140083c73  mov     ebx, eax
0x140083c75  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140083c7c  lea     rdi, WPP_8d19556b374b3e85e4187adf480561f2_Traceguids
0x140083c83  jz      short loc_140083CA7
0x140083c85  mov     rcx, [rsi+8]
0x140083c89  mov     r9d, 0Eh
0x140083c8f  mov     [rsp+0C0h+var_98], eax
0x140083c93  mov     dl, 2
0x140083c95  mov     [rsp+0C0h+var_A0], rdi
0x140083c9a  mov     rcx, [rcx+48h]
0x140083c9e  lea     r8d, [r9+4]
0x140083ca2  call    WPP_RECORDER_SF_d
0x140083ca7  test    ebx, ebx
0x140083ca9  js      loc_140083B42
0x140083caf  jmp     loc_140083B86
0x140083cb4  mov     dword ptr [rdi+0Ch], 0
0x140083cbb  mov     rax, qword ptr [rbp+57h+var_88+8]
0x140083cbf  mov     [rdi], rax
0x140083cc2  mov     rax, [rbp+57h+var_78]
0x140083cc6  mov     [rdi+10h], rax
0x140083cca  mov     rax, [rbp+57h+var_90]
0x140083cce  mov     [rdi+18h], rax
0x140083cd2  mov     [rdi+8], r14d
0x140083cd6  jmp     loc_140083B86
```
