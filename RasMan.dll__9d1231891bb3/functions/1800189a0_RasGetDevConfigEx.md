# RasGetDevConfigEx

- ea: `0x1800189a0`
- end: `0x180018a79`
- name: `RasGetDevConfigEx`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180002f80`
- `0x1800189a0`
- `0x180021000`
- `0x180021488`

## pseudocode

```c
__int64 __fastcall RasGetDevConfigEx(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 666, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  v8 = SubmitLocalRequest(0x7Bu, a1, a2, a3, a4);
  v9 = v8;
  if ( !v8 )
    goto LABEL_10;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 667, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v8);
LABEL_10:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 668, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x1800189a0  push    rbx
0x1800189a2  push    rbp
0x1800189a3  push    rsi
0x1800189a4  push    rdi
0x1800189a5  push    r15
0x1800189a7  sub     rsp, 30h
0x1800189ab  mov     rdi, r9
0x1800189ae  mov     rsi, r8
0x1800189b1  mov     rbp, rdx
0x1800189b4  mov     rbx, rcx
0x1800189b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800189be  lea     r15, WPP_GLOBAL_Control
0x1800189c5  cmp     rcx, r15
0x1800189c8  jz      short loc_1800189EE
0x1800189ca  test    byte ptr [rcx+1Ch], 40h
0x1800189ce  jz      short loc_1800189EE
0x1800189d0  cmp     byte ptr [rcx+19h], 6
0x1800189d4  jb      short loc_1800189EE
0x1800189d6  mov     rcx, [rcx+10h]
0x1800189da  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800189e1  mov     edx, 29Ah
0x1800189e6  mov     r9, rbx
0x1800189e9  call    WPP_SF_q
0x1800189ee  mov     ecx, 7Bh ; '{'
0x1800189f3  mov     [rsp+58h+var_38], rdi
0x1800189f8  mov     r9, rsi
0x1800189fb  mov     r8, rbp
0x1800189fe  mov     rdx, rbx
0x180018a01  call    SubmitLocalRequest
0x180018a06  mov     ebx, eax
0x180018a08  test    eax, eax
0x180018a0a  jz      short loc_180018A3C
0x180018a0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a13  cmp     rcx, r15
0x180018a16  jz      short loc_180018A6C
0x180018a18  test    byte ptr [rcx+1Ch], 40h
0x180018a1c  jz      short loc_180018A43
0x180018a1e  cmp     byte ptr [rcx+19h], 2
0x180018a22  jb      short loc_180018A43
0x180018a24  mov     rcx, [rcx+10h]
0x180018a28  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180018a2f  mov     edx, 29Bh
0x180018a34  mov     r9d, eax
0x180018a37  call    WPP_SF_d
0x180018a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a43  cmp     rcx, r15
0x180018a46  jz      short loc_180018A6C
0x180018a48  test    byte ptr [rcx+1Ch], 40h
0x180018a4c  jz      short loc_180018A6C
0x180018a4e  cmp     byte ptr [rcx+19h], 6
0x180018a52  jb      short loc_180018A6C
0x180018a54  mov     rcx, [rcx+10h]
0x180018a58  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180018a5f  mov     edx, 29Ch
0x180018a64  mov     r9d, ebx
0x180018a67  call    WPP_SF_d
0x180018a6c  mov     eax, ebx
0x180018a6e  add     rsp, 30h
0x180018a72  pop     r15
0x180018a74  pop     rdi
0x180018a75  pop     rsi
0x180018a76  pop     rbp
0x180018a77  pop     rbx
0x180018a78  retn
```
