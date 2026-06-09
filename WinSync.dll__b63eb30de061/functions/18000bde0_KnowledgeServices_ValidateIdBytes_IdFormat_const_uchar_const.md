# KnowledgeServices::ValidateIdBytes(IdFormat const &,uchar const *)

- ea: `0x18000bde0`
- end: `0x18000bf91`
- name: `?ValidateIdBytes@KnowledgeServices@@SAJAEBUIdFormat@@PEBE@Z`
- size: `433`
- prototype: `__int64 __fastcall(const struct IdFormat *, const unsigned __int8 *)`
- caller_count: `25`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180001120`
- `0x1800073c0`
- `0x180008ad0`
- `0x18000a4b0`
- `0x18000bb40`
- `0x18000bfa0`
- `0x180020320`
- `0x180084324`
- `0x1800849e0`
- `0x180084c70`
- `0x180084e7c`
- `0x180084f20`
- `0x1800852e0`
- `0x180085470`
- `0x1800855e0`
- `0x180085840`
- `0x1800867a0`
- `0x180086980`
- `0x180086f60`
- `0x180088670`
- `0x180088ad0`
- `0x18008c978`
- `0x180091448`
- `0x1800916fc`
- `0x180091a2c`

## callees

- `0x18000bde0`
- `0x18000f810`
- `0x18001a038`
- `0x18001ae20`

## string_xrefs

- `0x18000bf3d`: `KnowledgeServices::ValidateIdBytes`
- `0x18000bf70`: `KnowledgeServices::ValidateIdBytes`

## pseudocode

```c
__int64 __fastcall KnowledgeServices::ValidateIdBytes(const struct IdFormat *a1, unsigned __int8 *a2)
{
  PVOID *v4; // r10
  _WORD *v5; // rcx
  unsigned int v6; // edi
  int v7; // esi
  int v8; // r8d
  unsigned __int16 v9; // dx
  const unsigned __int8 *v10; // rcx
  const unsigned __int8 *v12; // rcx

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_e65626ae806d36e8966776faf765a664_Traceguids,
      "KnowledgeServices::ValidateIdBytes");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    v6 = -2147467261;
    goto LABEL_7;
  }
  v5 = (_WORD *)((char *)a1 + 4);
  if ( *(_DWORD *)a1 )
  {
    if ( *v5 <= 2u || *(_WORD *)a2 <= 2u || *(_WORD *)a2 > *v5 )
      goto LABEL_6;
  }
  else if ( !*v5 )
  {
LABEL_6:
    v6 = -2147217408;
LABEL_7:
    a2 = 0;
    v7 = 0;
    goto LABEL_17;
  }
  v8 = (unsigned __int16)*v5 | ((*(_DWORD *)a1 & 1 | 2) << 16);
  v7 = v8;
  if ( (((*(_DWORD *)a1 & 1 | 2) << 16) & 0x10000) == 0 )
    goto LABEL_12;
  v12 = a2;
  if ( (v8 & 0x20000) == 0 )
    v12 = a2 + 4;
  if ( *(_WORD *)v12 < (unsigned __int16)v8 )
  {
    v6 = 0;
  }
  else
  {
LABEL_12:
    v9 = (((*(_DWORD *)a1 & 1 | 2) << 16) & 0x10000) != 0 ? 2 : 0;
    v6 = 0;
    while ( v9 < (unsigned __int16)v8 )
    {
      v10 = a2;
      if ( (v8 & 0x20000) == 0 )
        v10 = a2 + 4;
      if ( v10[v9] != 0xFF )
        goto LABEL_17;
      ++v9;
    }
    v6 = -2147024809;
  }
LABEL_17:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      11,
      (unsigned int)WPP_e65626ae806d36e8966776faf765a664_Traceguids,
      (unsigned int)"KnowledgeServices::ValidateIdBytes",
      v6);
  if ( (v7 & 0x20000) == 0 && a2 && _InterlockedExchangeAdd((volatile signed __int32 *)a2, 0xFFFFFFFF) == 1 )
    SeFree(a2);
  return v6;
}

```

## disassembly

```asm
0x18000bde0  mov     [rsp+arg_0], rbx
0x18000bde5  mov     [rsp+arg_10], rbp
0x18000bdea  push    rsi
0x18000bdeb  push    rdi
0x18000bdec  push    r15
0x18000bdee  sub     rsp, 40h
0x18000bdf2  mov     rbx, rdx
0x18000bdf5  mov     rdi, rcx
0x18000bdf8  mov     r10, cs:WPP_GLOBAL_Control
0x18000bdff  lea     r15, WPP_GLOBAL_Control
0x18000be06  mov     ebp, 1
0x18000be0b  cmp     r10, r15
0x18000be0e  jz      short loc_18000BE1A
0x18000be10  test    [r10+1Ch], bpl
0x18000be14  jnz     loc_18000BF2E
0x18000be1a  test    rbx, rbx
0x18000be1d  jz      loc_18000BF24
0x18000be23  cmp     dword ptr [rdi], 0
0x18000be26  lea     rcx, [rdi+4]
0x18000be2a  mov     r11d, 2
0x18000be30  jnz     short loc_18000BE44
0x18000be32  xor     eax, eax
0x18000be34  cmp     ax, [rcx]
0x18000be37  jnz     short loc_18000BE58
0x18000be39  mov     edi, 80041000h
0x18000be3e  xor     ebx, ebx
0x18000be40  xor     esi, esi
0x18000be42  jmp     short loc_18000BEBA
0x18000be44  cmp     [rcx], r11w
0x18000be48  jbe     short loc_18000BE39
0x18000be4a  movzx   eax, word ptr [rbx]
0x18000be4d  cmp     ax, r11w
0x18000be51  jbe     short loc_18000BE39
0x18000be53  cmp     ax, [rcx]
0x18000be56  ja      short loc_18000BE39
0x18000be58  movzx   eax, word ptr [rcx]
0x18000be5b  mov     r8d, [rdi]
0x18000be5e  and     r8d, ebp
0x18000be61  mov     [rsp+58h+var_24], 0
0x18000be69  or      r8d, r11d
0x18000be6c  mov     word ptr [rsp+58h+var_24], ax
0x18000be71  mov     eax, [rsp+58h+var_24]
0x18000be75  shl     r8d, 10h
0x18000be79  btr     eax, 10h
0x18000be7d  or      r8d, eax
0x18000be80  mov     r9d, r8d
0x18000be83  mov     esi, r8d
0x18000be86  and     r9d, 10000h
0x18000be8d  jnz     short loc_18000BEF4
0x18000be8f  neg     r9d
0x18000be92  sbb     dx, dx
0x18000be95  and     dx, r11w
0x18000be99  xor     edi, edi
0x18000be9b  cmp     dx, r8w
0x18000be9f  jnb     short loc_18000BF1D
0x18000bea1  bt      r8d, 11h
0x18000bea6  lea     rax, [rbx+4]
0x18000beaa  mov     rcx, rbx
0x18000bead  cmovnb  rcx, rax
0x18000beb1  movzx   eax, dx
0x18000beb4  cmp     byte ptr [rcx+rax], 0FFh
0x18000beb8  jz      short loc_18000BF0E
0x18000beba  cmp     r10, r15
0x18000bebd  jz      short loc_18000BEC9
0x18000bebf  test    [r10+1Ch], bpl
0x18000bec3  jnz     loc_18000BF61
0x18000bec9  bt      esi, 11h
0x18000becd  jb      short loc_18000BEDF
0x18000becf  test    rbx, rbx
0x18000bed2  jz      short loc_18000BEDF
0x18000bed4  or      edx, 0FFFFFFFFh
0x18000bed7  lock xadd [rbx], edx
0x18000bedb  cmp     edx, ebp
0x18000bedd  jz      short loc_18000BF13
0x18000bedf  mov     rbx, [rsp+58h+arg_0]
0x18000bee4  mov     eax, edi
0x18000bee6  mov     rbp, [rsp+58h+arg_10]
0x18000beeb  add     rsp, 40h
0x18000beef  pop     r15
0x18000bef1  pop     rdi
0x18000bef2  pop     rsi
0x18000bef3  retn
0x18000bef4  bt      r8d, 11h
0x18000bef9  lea     rax, [rbx+4]
0x18000befd  mov     rcx, rbx
0x18000bf00  cmovnb  rcx, rax
0x18000bf04  cmp     [rcx], r8w
0x18000bf08  jnb     short loc_18000BE8F
0x18000bf0a  xor     edi, edi
0x18000bf0c  jmp     short loc_18000BEBA
0x18000bf0e  add     dx, bp
0x18000bf11  jmp     short loc_18000BE9B
0x18000bf13  mov     rcx, rbx; void *
0x18000bf16  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x18000bf1b  jmp     short loc_18000BEDF
0x18000bf1d  mov     edi, 80070057h
0x18000bf22  jmp     short loc_18000BEBA
0x18000bf24  mov     edi, 80004003h
0x18000bf29  jmp     loc_18000BE3E
0x18000bf2e  cmp     byte ptr [r10+19h], 5
0x18000bf33  jb      loc_18000BE1A
0x18000bf39  mov     rcx, [r10+10h]
0x18000bf3d  lea     r9, aKnowledgeservi_4; "KnowledgeServices::ValidateIdBytes"
0x18000bf44  mov     edx, 0Ah
0x18000bf49  lea     r8, WPP_e65626ae806d36e8966776faf765a664_Traceguids
0x18000bf50  call    WPP_SF_s
0x18000bf55  mov     r10, cs:WPP_GLOBAL_Control
0x18000bf5c  jmp     loc_18000BE1A
0x18000bf61  cmp     byte ptr [r10+19h], 5
0x18000bf66  jb      loc_18000BEC9
0x18000bf6c  mov     rcx, [r10+10h]
0x18000bf70  lea     r9, aKnowledgeservi_4; "KnowledgeServices::ValidateIdBytes"
0x18000bf77  mov     edx, 0Bh
0x18000bf7c  mov     [rsp+58h+var_38], edi
0x18000bf80  lea     r8, WPP_e65626ae806d36e8966776faf765a664_Traceguids
0x18000bf87  call    WPP_SF_sD
0x18000bf8c  jmp     loc_18000BEC9
```
