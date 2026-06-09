# RasCompressionSetInfo

- ea: `0x180016c30`
- end: `0x180016d3b`
- name: `RasCompressionSetInfo`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x180016c30`
- `0x180021000`
- `0x180021488`

## pseudocode

```c
__int64 __fastcall RasCompressionSetInfo(__int64 a1, __int64 a2, __int64 a3)
{
  PVOID *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  unsigned int v9; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 271, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v7 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 272;
LABEL_20:
      WPP_SF_d(v6[2], v8, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
      return v7;
    }
    return v7;
  }
  v9 = SubmitLocalRequest(0x14u, a1, a2, a3);
  v7 = v9;
  if ( v9 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v7;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 273, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 6u )
  {
    v8 = 274;
    goto LABEL_20;
  }
  return v7;
}

```

## disassembly

```asm
0x180016c30  push    rbx
0x180016c32  push    rsi
0x180016c33  push    rdi
0x180016c34  push    r14
0x180016c36  sub     rsp, 28h
0x180016c3a  mov     rdi, r8
0x180016c3d  mov     rsi, rdx
0x180016c40  mov     rbx, rcx
0x180016c43  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c4a  lea     r14, WPP_GLOBAL_Control
0x180016c51  cmp     rcx, r14
0x180016c54  jz      short loc_180016C7A
0x180016c56  test    byte ptr [rcx+1Ch], 40h
0x180016c5a  jz      short loc_180016C7A
0x180016c5c  cmp     byte ptr [rcx+19h], 6
0x180016c60  jb      short loc_180016C7A
0x180016c62  mov     rcx, [rcx+10h]
0x180016c66  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180016c6d  mov     edx, 10Fh
0x180016c72  mov     r9, rbx
0x180016c75  call    WPP_SF_q
0x180016c7a  mov     rcx, rbx
0x180016c7d  call    ValidatePortHandle
0x180016c82  test    eax, eax
0x180016c84  jnz     short loc_180016CB6
0x180016c86  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c8d  mov     ebx, 259h
0x180016c92  cmp     rcx, r14
0x180016c95  jz      loc_180016D2F
0x180016c9b  test    byte ptr [rcx+1Ch], 40h
0x180016c9f  jz      loc_180016D2F
0x180016ca5  cmp     byte ptr [rcx+19h], 2
0x180016ca9  jb      loc_180016D2F
0x180016caf  mov     edx, 110h
0x180016cb4  jmp     short loc_180016D1C
0x180016cb6  mov     ecx, 14h
0x180016cbb  mov     r9, rdi
0x180016cbe  mov     r8, rsi
0x180016cc1  mov     rdx, rbx
0x180016cc4  call    SubmitLocalRequest
0x180016cc9  mov     ebx, eax
0x180016ccb  test    eax, eax
0x180016ccd  jz      short loc_180016CFF
0x180016ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cd6  cmp     rcx, r14
0x180016cd9  jz      short loc_180016D2F
0x180016cdb  test    byte ptr [rcx+1Ch], 40h
0x180016cdf  jz      short loc_180016D06
0x180016ce1  cmp     byte ptr [rcx+19h], 2
0x180016ce5  jb      short loc_180016D06
0x180016ce7  mov     rcx, [rcx+10h]
0x180016ceb  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180016cf2  mov     edx, 111h
0x180016cf7  mov     r9d, eax
0x180016cfa  call    WPP_SF_d
0x180016cff  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d06  cmp     rcx, r14
0x180016d09  jz      short loc_180016D2F
0x180016d0b  test    byte ptr [rcx+1Ch], 40h
0x180016d0f  jz      short loc_180016D2F
0x180016d11  cmp     byte ptr [rcx+19h], 6
0x180016d15  jb      short loc_180016D2F
0x180016d17  mov     edx, 112h
0x180016d1c  mov     rcx, [rcx+10h]
0x180016d20  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180016d27  mov     r9d, ebx
0x180016d2a  call    WPP_SF_d
0x180016d2f  mov     eax, ebx
0x180016d31  add     rsp, 28h
0x180016d35  pop     r14
0x180016d37  pop     rdi
0x180016d38  pop     rsi
0x180016d39  pop     rbx
0x180016d3a  retn
```
