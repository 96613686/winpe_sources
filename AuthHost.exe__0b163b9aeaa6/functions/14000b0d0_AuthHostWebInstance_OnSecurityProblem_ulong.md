# AuthHostWebInstance::OnSecurityProblem(ulong)

- ea: `0x14000b0d0`
- end: `0x14000b2ff`
- name: `?OnSecurityProblem@AuthHostWebInstance@@UEAAJK@Z`
- size: `559`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140006748`
- `0x140006a24`
- `0x14000b0d0`
- `0x14000b840`
- `0x14000c764`
- `0x140012f60`
- `0x140014010`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::OnSecurityProblem(AuthHostWebInstance *this, int a2, __int64 a3)
{
  PVOID *v5; // rcx
  unsigned int v6; // edi
  bool v7; // zf
  __int64 *v8; // rdx
  int v10; // [rsp+30h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+38h] [rbp-28h] BYREF
  int *v12; // [rsp+48h] [rbp-18h]
  __int64 v13; // [rsp+50h] [rbp-10h]

  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 55, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  v6 = -2147467260;
  if ( (unsigned int)a2 > 0x2F14 )
  {
    if ( a2 == 12055 )
    {
      a2 = -2146697191;
      goto LABEL_39;
    }
    if ( a2 != 12057 )
    {
      if ( a2 != 12168 )
      {
        if ( a2 == 12169 )
        {
          a2 = -2146762480;
          goto LABEL_39;
        }
        if ( a2 == 12170 )
        {
          a2 = -2146885616;
          goto LABEL_39;
        }
      }
      goto LABEL_31;
    }
    goto LABEL_35;
  }
  switch ( a2 )
  {
    case 12052:
      goto LABEL_35;
    case 12037:
      a2 = -2146762495;
      goto LABEL_39;
    case 12038:
      a2 = -2146762481;
      goto LABEL_39;
    case 12039:
LABEL_35:
      v6 = -2147417847;
      goto LABEL_36;
  }
  if ( a2 != 12044 )
  {
    if ( a2 == 12045 )
    {
      a2 = -2146762487;
      goto LABEL_39;
    }
LABEL_31:
    v7 = a2 == 0;
    if ( a2 > 0 )
    {
      a2 = (unsigned __int16)a2 | 0x80070000;
      v7 = a2 == 0;
    }
    if ( v7 )
    {
LABEL_40:
      if ( (Microsoft_Windows_WebAuthEnableBits & 2) != 0 )
      {
        v8 = SecurityProblemAbortEvent;
        goto LABEL_42;
      }
      return v6;
    }
LABEL_39:
    AuthHostWebInstance::TerminateNavigate((AuthHostWebInstance *)((char *)this - 16), &szColor, a2);
    goto LABEL_40;
  }
  if ( (*((_DWORD *)this + 28) & 0x100000) != 0 )
  {
    v6 = 1;
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 11) + 96LL))(*((_QWORD *)this + 11), 1);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_DdD(*((_QWORD *)WPP_GLOBAL_Control + 7), 56);
    }
    return v6;
  }
  v6 = -2147417847;
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 68) & 4) != 0 && *((_BYTE *)v5 + 65) >= 5u )
    WPP_SF_DdD(v5[7], 57);
LABEL_36:
  if ( (Microsoft_Windows_WebAuthEnableBits & 4) != 0 )
  {
    v8 = SecurityProblemRetryEvent;
LABEL_42:
    v10 = a2;
    v12 = &v10;
    v13 = 4;
    McGenEventWrite_EventWriteTransfer((__int64)v5, (const EVENT_DESCRIPTOR *)v8, a3, 2u, &v11);
  }
  return v6;
}

```

## disassembly

```asm
0x14000b0d0  mov     [rsp-18h+arg_10], rbx
0x14000b0d5  mov     [rsp-18h+arg_18], rsi
0x14000b0da  push    rbp
0x14000b0db  push    rdi
0x14000b0dc  push    r12
0x14000b0de  mov     rbp, rsp
0x14000b0e1  sub     rsp, 60h
0x14000b0e5  mov     rax, cs:__security_cookie
0x14000b0ec  xor     rax, rsp
0x14000b0ef  mov     [rbp+var_8], rax
0x14000b0f3  mov     ebx, edx
0x14000b0f5  mov     rsi, rcx
0x14000b0f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b0ff  lea     r12, WPP_GLOBAL_Control
0x14000b106  cmp     rcx, r12
0x14000b109  jz      short loc_14000B13A
0x14000b10b  test    byte ptr [rcx+44h], 4
0x14000b10f  jz      short loc_14000B13A
0x14000b111  cmp     byte ptr [rcx+41h], 2
0x14000b115  jb      short loc_14000B13A
0x14000b117  mov     rcx, [rcx+38h]
0x14000b11b  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000b122  mov     edx, 37h ; '7'
0x14000b127  mov     dword ptr [rsp+60h+var_40], ebx
0x14000b12b  mov     r9d, ebx
0x14000b12e  call    WPP_SF_Dd
0x14000b133  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b13a  mov     eax, 2F14h
0x14000b13f  mov     edi, 80004004h
0x14000b144  cmp     ebx, eax
0x14000b146  ja      loc_14000B238
0x14000b14c  jz      loc_14000B276
0x14000b152  mov     eax, ebx
0x14000b154  sub     eax, 2F05h
0x14000b159  jz      loc_14000B231
0x14000b15f  sub     eax, 1
0x14000b162  jz      loc_14000B22A
0x14000b168  sub     eax, 1
0x14000b16b  jz      loc_14000B276
0x14000b171  sub     eax, 5
0x14000b174  jz      short loc_14000B189
0x14000b176  cmp     eax, 1
0x14000b179  jnz     loc_14000B263
0x14000b17f  mov     ebx, 800B0109h
0x14000b184  jmp     loc_14000B292
0x14000b189  test    dword ptr [rsi+70h], 100000h
0x14000b190  jz      short loc_14000B1ED
0x14000b192  mov     rcx, [rsi+58h]
0x14000b196  mov     edi, 1
0x14000b19b  mov     edx, edi
0x14000b19d  mov     rax, [rcx]
0x14000b1a0  mov     rax, [rax+60h]
0x14000b1a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b1a9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b1b0  cmp     rcx, r12
0x14000b1b3  jz      loc_14000B2DC
0x14000b1b9  test    byte ptr [rcx+44h], 4
0x14000b1bd  jz      loc_14000B2DC
0x14000b1c3  cmp     byte ptr [rcx+41h], 5
0x14000b1c7  jb      loc_14000B2DC
0x14000b1cd  mov     rcx, [rcx+38h]
0x14000b1d1  lea     edx, [rdi+37h]
0x14000b1d4  mov     r9d, 2F0Ch
0x14000b1da  mov     [rsp+60h+var_38], edi
0x14000b1de  mov     dword ptr [rsp+60h+var_40], r9d
0x14000b1e3  call    WPP_SF_DdD
0x14000b1e8  jmp     loc_14000B2DC
0x14000b1ed  mov     edi, 80010109h
0x14000b1f2  cmp     rcx, r12
0x14000b1f5  jz      loc_14000B27B
0x14000b1fb  test    byte ptr [rcx+44h], 4
0x14000b1ff  jz      short loc_14000B27B
0x14000b201  cmp     byte ptr [rcx+41h], 5
0x14000b205  jb      short loc_14000B27B
0x14000b207  mov     rcx, [rcx+38h]
0x14000b20b  mov     r9d, 2F0Ch
0x14000b211  mov     edx, 39h ; '9'
0x14000b216  mov     [rsp+60h+var_38], 80010109h
0x14000b21e  mov     dword ptr [rsp+60h+var_40], r9d
0x14000b223  call    WPP_SF_DdD
0x14000b228  jmp     short loc_14000B27B
0x14000b22a  mov     ebx, 800B010Fh
0x14000b22f  jmp     short loc_14000B292
0x14000b231  mov     ebx, 800B0101h
0x14000b236  jmp     short loc_14000B292
0x14000b238  mov     eax, ebx
0x14000b23a  sub     eax, 2F17h
0x14000b23f  jz      short loc_14000B28D
0x14000b241  sub     eax, 2
0x14000b244  jz      short loc_14000B276
0x14000b246  sub     eax, 6Fh ; 'o'
0x14000b249  jz      short loc_14000B263
0x14000b24b  sub     eax, 1
0x14000b24e  jz      short loc_14000B25C
0x14000b250  cmp     eax, 1
0x14000b253  jnz     short loc_14000B263
0x14000b255  mov     ebx, 80092010h
0x14000b25a  jmp     short loc_14000B292
0x14000b25c  mov     ebx, 800B0110h
0x14000b261  jmp     short loc_14000B292
0x14000b263  test    ebx, ebx
0x14000b265  jle     short loc_14000B272
0x14000b267  movzx   ebx, bx
0x14000b26a  or      ebx, 80070000h
0x14000b270  test    ebx, ebx
0x14000b272  jz      short loc_14000B2A5
0x14000b274  jmp     short loc_14000B292
0x14000b276  mov     edi, 80010109h
0x14000b27b  test    cs:Microsoft_Windows_WebAuthEnableBits, 4
0x14000b282  jz      short loc_14000B2DC
0x14000b284  lea     rdx, SecurityProblemRetryEvent
0x14000b28b  jmp     short loc_14000B2B5
0x14000b28d  mov     ebx, 800C0019h
0x14000b292  lea     rcx, [rsi-10h]; this
0x14000b296  mov     r8d, ebx; unsigned int
0x14000b299  lea     rdx, szColor; unsigned __int16 *
0x14000b2a0  call    ?TerminateNavigate@AuthHostWebInstance@@AEAAXPEBGK@Z; AuthHostWebInstance::TerminateNavigate(ushort const *,ulong)
0x14000b2a5  test    cs:Microsoft_Windows_WebAuthEnableBits, 2
0x14000b2ac  jz      short loc_14000B2DC
0x14000b2ae  lea     rdx, SecurityProblemAbortEvent
0x14000b2b5  lea     rax, [rbp+var_30]
0x14000b2b9  mov     [rbp+var_30], ebx
0x14000b2bc  mov     [rbp+var_18], rax
0x14000b2c0  mov     r9d, 2
0x14000b2c6  lea     rax, [rbp+var_28]
0x14000b2ca  mov     [rbp+var_10], 4
0x14000b2d2  mov     [rsp+60h+var_40], rax
0x14000b2d7  call    McGenEventWrite_EventWriteTransfer
0x14000b2dc  mov     eax, edi
0x14000b2de  mov     rcx, [rbp+var_8]
0x14000b2e2  xor     rcx, rsp; StackCookie
0x14000b2e5  call    __security_check_cookie
0x14000b2ea  lea     r11, [rsp+60h+var_s0]
0x14000b2ef  mov     rbx, [r11+30h]
0x14000b2f3  mov     rsi, [r11+38h]
0x14000b2f7  mov     rsp, r11
0x14000b2fa  pop     r12
0x14000b2fc  pop     rdi
0x14000b2fd  pop     rbp
0x14000b2fe  retn
```
