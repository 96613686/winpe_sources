# RasUpdateAutoTriggerRegKeys

- ea: `0x180020750`
- end: `0x1800208a4`
- name: `RasUpdateAutoTriggerRegKeys`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180002f80`
- `0x180020750`
- `0x180021000`
- `0x180021118`

## pseudocode

```c
__int64 __fastcall RasUpdateAutoTriggerRegKeys(
        __int64 a1,
        const char *a2,
        __int64 a3,
        int a4,
        int a5,
        const char *a6,
        int a7)
{
  const char *v11; // r11
  const char *v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  PVOID *v15; // rcx
  __int64 v17; // [rsp+20h] [rbp-78h]
  __int64 v18; // [rsp+28h] [rbp-70h]
  __int64 v19; // [rsp+38h] [rbp-60h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v11 = a6;
    v12 = a2;
    if ( !a6 )
      v11 = L"<NULL>";
    if ( !a2 )
      v12 = L"<NULL>";
    WPP_SF_SScccS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v12, a4 != 0, a5 != 0, a7 != 0, (__int64)v11);
  }
  LODWORD(v19) = a7;
  LODWORD(v18) = a5;
  LODWORD(v17) = a4;
  v13 = SubmitLocalRequest(0x91u, a1, a2, a3, v17, v18, a6, v19);
  v14 = v13;
  if ( !v13 )
    goto LABEL_14;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v14;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 707, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v13);
LABEL_14:
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x40) != 0 && *((_BYTE *)v15 + 25) >= 6u )
    WPP_SF_d(v15[2], 708, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x180020750  push    rbx
0x180020752  push    rbp
0x180020753  push    rsi
0x180020754  push    rdi
0x180020755  push    r12
0x180020757  push    r13
0x180020759  push    r14
0x18002075b  push    r15
0x18002075d  sub     rsp, 58h
0x180020761  mov     ebp, r9d
0x180020764  mov     r12, r8
0x180020767  mov     rbx, rdx
0x18002076a  mov     rdi, rcx
0x18002076d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020774  lea     r13, WPP_GLOBAL_Control
0x18002077b  mov     r14d, [rsp+98h+arg_30]
0x180020783  mov     rsi, [rsp+98h+arg_28]
0x18002078b  mov     r15d, [rsp+98h+arg_20]
0x180020793  cmp     rcx, r13
0x180020796  jz      short loc_180020805
0x180020798  test    byte ptr [rcx+1Ch], 40h
0x18002079c  jz      short loc_180020805
0x18002079e  cmp     byte ptr [rcx+19h], 6
0x1800207a2  jb      short loc_180020805
0x1800207a4  mov     rcx, [rcx+10h]; LoggerHandle
0x1800207a8  lea     r13, aNull_2; "<NULL>"
0x1800207af  test    rsi, rsi
0x1800207b2  mov     r11, rsi
0x1800207b5  mov     rax, rbx
0x1800207b8  cmovz   r11, r13
0x1800207bc  test    r14d, r14d
0x1800207bf  mov     [rsp+98h+var_58], r11; __int64
0x1800207c4  setnz   r10b
0x1800207c8  test    r15d, r15d
0x1800207cb  mov     [rsp+98h+var_60], r10b; char
0x1800207d0  setnz   r8b
0x1800207d4  test    r9d, r9d
0x1800207d7  mov     [rsp+98h+var_68], r8b; char
0x1800207dc  mov     r9, rdi
0x1800207df  setnz   dl
0x1800207e2  test    rbx, rbx
0x1800207e5  mov     [rsp+98h+var_70], dl; char
0x1800207e9  cmovz   rax, r13
0x1800207ed  test    rdi, rdi
0x1800207f0  mov     [rsp+98h+var_78], rax; __int64
0x1800207f5  cmovz   r9, r13
0x1800207f9  call    WPP_SF_SScccS
0x1800207fe  lea     r13, WPP_GLOBAL_Control
0x180020805  mov     dword ptr [rsp+98h+var_60], r14d
0x18002080a  mov     ecx, 91h
0x18002080f  mov     qword ptr [rsp+98h+var_68], rsi
0x180020814  mov     r9, r12
0x180020817  mov     dword ptr [rsp+98h+var_70], r15d
0x18002081c  mov     r8, rbx
0x18002081f  mov     rdx, rdi
0x180020822  mov     dword ptr [rsp+98h+var_78], ebp
0x180020826  call    SubmitLocalRequest
0x18002082b  mov     ebx, eax
0x18002082d  test    eax, eax
0x18002082f  jz      short loc_180020861
0x180020831  mov     rcx, cs:WPP_GLOBAL_Control
0x180020838  cmp     rcx, r13
0x18002083b  jz      short loc_180020891
0x18002083d  test    byte ptr [rcx+1Ch], 40h
0x180020841  jz      short loc_180020868
0x180020843  cmp     byte ptr [rcx+19h], 2
0x180020847  jb      short loc_180020868
0x180020849  mov     rcx, [rcx+10h]
0x18002084d  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020854  mov     edx, 2C3h
0x180020859  mov     r9d, eax
0x18002085c  call    WPP_SF_d
0x180020861  mov     rcx, cs:WPP_GLOBAL_Control
0x180020868  cmp     rcx, r13
0x18002086b  jz      short loc_180020891
0x18002086d  test    byte ptr [rcx+1Ch], 40h
0x180020871  jz      short loc_180020891
0x180020873  cmp     byte ptr [rcx+19h], 6
0x180020877  jb      short loc_180020891
0x180020879  mov     rcx, [rcx+10h]
0x18002087d  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020884  mov     edx, 2C4h
0x180020889  mov     r9d, ebx
0x18002088c  call    WPP_SF_d
0x180020891  mov     eax, ebx
0x180020893  add     rsp, 58h
0x180020897  pop     r15
0x180020899  pop     r14
0x18002089b  pop     r13
0x18002089d  pop     r12
0x18002089f  pop     rdi
0x1800208a0  pop     rsi
0x1800208a1  pop     rbp
0x1800208a2  pop     rbx
0x1800208a3  retn
```
