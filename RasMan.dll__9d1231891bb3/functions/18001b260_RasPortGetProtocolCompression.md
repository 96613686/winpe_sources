# RasPortGetProtocolCompression

- ea: `0x18001b260`
- end: `0x18001b378`
- name: `RasPortGetProtocolCompression`
- size: `280`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002f80`
- `0x1800119c4`
- `0x18001b260`
- `0x180021000`
- `0x1800217a0`

## pseudocode

```c
__int64 __fastcall RasPortGetProtocolCompression(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  PVOID *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int v11; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 316, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1, a2);
  }
  if ( !(unsigned int)ValidatePortHandle(a1) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v9 = 601;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = 317;
LABEL_20:
      WPP_SF_d(v8[2], v10, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
      return v9;
    }
    return v9;
  }
  v11 = SubmitLocalRequest(0x2Au, a1, a2, a3, a4);
  v9 = v11;
  if ( v11 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v9;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_16;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 318, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v11);
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_16:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 6u )
  {
    v10 = 319;
    goto LABEL_20;
  }
  return v9;
}

```

## disassembly

```asm
0x18001b260  push    rbx
0x18001b262  push    rbp
0x18001b263  push    rsi
0x18001b264  push    rdi
0x18001b265  push    r15
0x18001b267  sub     rsp, 30h
0x18001b26b  mov     rsi, r9
0x18001b26e  mov     rbp, r8
0x18001b271  mov     edi, edx
0x18001b273  mov     rbx, rcx
0x18001b276  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b27d  lea     r15, WPP_GLOBAL_Control
0x18001b284  cmp     rcx, r15
0x18001b287  jz      short loc_18001B2B1
0x18001b289  test    byte ptr [rcx+1Ch], 40h
0x18001b28d  jz      short loc_18001B2B1
0x18001b28f  cmp     byte ptr [rcx+19h], 6
0x18001b293  jb      short loc_18001B2B1
0x18001b295  mov     rcx, [rcx+10h]
0x18001b299  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b2a0  mov     edx, 13Ch
0x18001b2a5  mov     dword ptr [rsp+58h+var_38], edi
0x18001b2a9  mov     r9, rbx
0x18001b2ac  call    WPP_SF_qd
0x18001b2b1  mov     rcx, rbx
0x18001b2b4  call    ValidatePortHandle
0x18001b2b9  test    eax, eax
0x18001b2bb  jnz     short loc_18001B2ED
0x18001b2bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2c4  mov     ebx, 259h
0x18001b2c9  cmp     rcx, r15
0x18001b2cc  jz      loc_18001B36B
0x18001b2d2  test    byte ptr [rcx+1Ch], 40h
0x18001b2d6  jz      loc_18001B36B
0x18001b2dc  cmp     byte ptr [rcx+19h], 2
0x18001b2e0  jb      loc_18001B36B
0x18001b2e6  mov     edx, 13Dh
0x18001b2eb  jmp     short loc_18001B358
0x18001b2ed  mov     ecx, 2Ah ; '*'
0x18001b2f2  mov     [rsp+58h+var_38], rsi
0x18001b2f7  mov     r9, rbp
0x18001b2fa  mov     r8d, edi
0x18001b2fd  mov     rdx, rbx
0x18001b300  call    SubmitLocalRequest
0x18001b305  mov     ebx, eax
0x18001b307  test    eax, eax
0x18001b309  jz      short loc_18001B33B
0x18001b30b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b312  cmp     rcx, r15
0x18001b315  jz      short loc_18001B36B
0x18001b317  test    byte ptr [rcx+1Ch], 40h
0x18001b31b  jz      short loc_18001B342
0x18001b31d  cmp     byte ptr [rcx+19h], 2
0x18001b321  jb      short loc_18001B342
0x18001b323  mov     rcx, [rcx+10h]
0x18001b327  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b32e  mov     edx, 13Eh
0x18001b333  mov     r9d, eax
0x18001b336  call    WPP_SF_d
0x18001b33b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b342  cmp     rcx, r15
0x18001b345  jz      short loc_18001B36B
0x18001b347  test    byte ptr [rcx+1Ch], 40h
0x18001b34b  jz      short loc_18001B36B
0x18001b34d  cmp     byte ptr [rcx+19h], 6
0x18001b351  jb      short loc_18001B36B
0x18001b353  mov     edx, 13Fh
0x18001b358  mov     rcx, [rcx+10h]
0x18001b35c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b363  mov     r9d, ebx
0x18001b366  call    WPP_SF_d
0x18001b36b  mov     eax, ebx
0x18001b36d  add     rsp, 30h
0x18001b371  pop     r15
0x18001b373  pop     rdi
0x18001b374  pop     rsi
0x18001b375  pop     rbp
0x18001b376  pop     rbx
0x18001b377  retn
```
