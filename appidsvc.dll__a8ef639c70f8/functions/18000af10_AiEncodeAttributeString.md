# AiEncodeAttributeString

- ea: `0x18000af10`
- end: `0x18000b092`
- name: `AiEncodeAttributeString`
- size: `386`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004c28`
- `0x180009a24`

## callees

- `0x18000880c`
- `0x18000af10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000afe7`
- `ntdll!RtlFreeHeap` at `0x18000afe7`

## pseudocode

```c
__int64 __fastcall AiEncodeAttributeString(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // esi
  unsigned __int16 v4; // di
  __int64 v7; // r9
  unsigned __int16 v8; // cx
  __int64 v9; // r12
  int v10; // edx
  unsigned __int16 v11; // r8
  unsigned __int16 v12; // dx
  __int64 v13; // rax
  _WORD *v14; // r8
  void *v15; // r8
  unsigned __int16 i; // r9
  __int16 v17; // cx
  unsigned __int8 v18; // dl

  v3 = 0;
  v4 = *(_WORD *)a1 >> 1;
  *(_OWORD *)a3 = 0;
  if ( v4 )
  {
    v7 = *(_QWORD *)(a1 + 8);
    v8 = 0;
    v9 = 0x400000020000109LL;
    v10 = 0;
    do
    {
      v11 = *(_WORD *)(v7 + 2LL * v8) - 34;
      if ( v11 <= 0x3Au && _bittest64(&v9, v11) )
        ++v10;
      ++v8;
    }
    while ( v8 < v4 );
    if ( v10 )
    {
      if ( (unsigned int)v4 + 2 * v10 > 0x7FFE )
      {
        v3 = -1073741675;
        goto LABEL_12;
      }
      v12 = *(_WORD *)a1 + 4 * v10;
      *(_WORD *)a3 = v12;
      v12 += 2;
      *(_WORD *)(a3 + 2) = v12;
      v13 = AiAlloc(v12);
      *(_QWORD *)(a3 + 8) = v13;
      v14 = (_WORD *)v13;
      if ( !v13 )
      {
        v3 = -1073741801;
LABEL_12:
        v15 = *(void **)(a3 + 8);
        if ( v15 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
          *(_OWORD *)a3 = 0;
        }
        return v3;
      }
      for ( i = 0; i < v4; ++i )
      {
        v17 = *(_WORD *)(*(_QWORD *)(a1 + 8) + 2LL * i);
        if ( (unsigned __int16)(v17 - 34) <= 0x3Au && _bittest64(&v9, (unsigned __int16)(v17 - 34)) )
        {
          *v14 = 37;
          v18 = *(_BYTE *)(*(_QWORD *)(a1 + 8) + 2LL * i);
          v14[2] = (v18 & 0xF) + ((v18 & 0xFu) < 0xA ? 48 : 55);
          v14[1] = (v18 >> 4) + ((unsigned __int8)(v18 >> 4) < 0xAu ? 48 : 55);
          v14 += 2;
        }
        else
        {
          *v14 = v17;
        }
        ++v14;
      }
      *v14 = 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000af10  push    rbx
0x18000af12  push    rbp
0x18000af13  push    rsi
0x18000af14  push    rdi
0x18000af15  push    r12
0x18000af17  push    r14
0x18000af19  push    r15
0x18000af1b  sub     rsp, 20h
0x18000af1f  movzx   edi, word ptr [rcx]
0x18000af22  xor     esi, esi
0x18000af24  shr     di, 1
0x18000af27  xor     eax, eax
0x18000af29  xorps   xmm0, xmm0
0x18000af2c  mov     rbx, r8
0x18000af2f  mov     r14, rcx
0x18000af32  movups  xmmword ptr [r8], xmm0
0x18000af36  cmp     ax, di
0x18000af39  jnb     loc_18000B081
0x18000af3f  mov     r9, [r14+8]
0x18000af43  lea     ebp, [rsi+1]
0x18000af46  xor     ecx, ecx
0x18000af48  mov     r12, 400000020000109h
0x18000af52  xor     edx, edx
0x18000af54  movzx   eax, cx
0x18000af57  movzx   r8d, word ptr [r9+rax*2]
0x18000af5c  sub     r8w, 22h ; '"'
0x18000af61  cmp     r8w, 3Ah ; ':'
0x18000af66  ja      short loc_18000AF74
0x18000af68  movzx   eax, r8w
0x18000af6c  bt      r12, rax
0x18000af70  jnb     short loc_18000AF74
0x18000af72  add     edx, ebp
0x18000af74  add     cx, bp
0x18000af77  cmp     cx, di
0x18000af7a  jb      short loc_18000AF54
0x18000af7c  test    edx, edx
0x18000af7e  jz      loc_18000B081
0x18000af84  movzx   eax, di
0x18000af87  lea     ecx, [rax+rdx*2]
0x18000af8a  cmp     ecx, 7FFEh
0x18000af90  jbe     short loc_18000AF99
0x18000af92  mov     esi, 0C0000095h
0x18000af97  jmp     short loc_18000AFCB
0x18000af99  shl     dx, 2
0x18000af9d  mov     r15d, 2
0x18000afa3  add     dx, [r14]
0x18000afa7  mov     [rbx], dx
0x18000afaa  add     dx, r15w
0x18000afae  movzx   ecx, dx
0x18000afb1  mov     [rbx+2], cx
0x18000afb5  call    AiAlloc
0x18000afba  mov     [rbx+8], rax
0x18000afbe  mov     r8, rax
0x18000afc1  test    rax, rax
0x18000afc4  jnz     short loc_18000AFF8
0x18000afc6  mov     esi, 0C0000017h
0x18000afcb  mov     r8, [rbx+8]; P
0x18000afcf  test    r8, r8
0x18000afd2  jz      loc_18000B081
0x18000afd8  mov     rcx, gs:60h
0x18000afe1  xor     edx, edx; Flags
0x18000afe3  mov     rcx, [rcx+30h]; HeapHandle
0x18000afe7  call    cs:__imp_RtlFreeHeap
0x18000afed  xorps   xmm0, xmm0
0x18000aff0  movups  xmmword ptr [rbx], xmm0
0x18000aff3  jmp     loc_18000B081
0x18000aff8  xor     r9d, r9d
0x18000affb  mov     r10w, 0FFF9h
0x18000b000  mov     rax, [r14+8]
0x18000b004  movzx   edx, r9w
0x18000b008  movzx   ecx, word ptr [rax+rdx*2]
0x18000b00c  lea     eax, [rcx-22h]
0x18000b00f  cmp     ax, 3Ah ; ':'
0x18000b013  ja      short loc_18000B06A
0x18000b015  movzx   eax, ax
0x18000b018  bt      r12, rax
0x18000b01c  jnb     short loc_18000B06A
0x18000b01e  mov     word ptr [r8], 25h ; '%'
0x18000b024  mov     rax, [r14+8]
0x18000b028  mov     dl, [rax+rdx*2]
0x18000b02b  mov     al, dl
0x18000b02d  and     al, 0Fh
0x18000b02f  movzx   ecx, al
0x18000b032  cmp     cl, 0Ah
0x18000b035  sbb     ax, ax
0x18000b038  shr     dl, 4
0x18000b03b  and     ax, r10w
0x18000b03f  add     ax, 37h ; '7'
0x18000b043  add     ax, cx
0x18000b046  movzx   ecx, dl
0x18000b049  mov     [r8+4], ax
0x18000b04e  cmp     cl, 0Ah
0x18000b051  sbb     ax, ax
0x18000b054  and     ax, r10w
0x18000b058  add     ax, 37h ; '7'
0x18000b05c  add     ax, cx
0x18000b05f  mov     [r8+2], ax
0x18000b064  add     r8, 4
0x18000b068  jmp     short loc_18000B06E
0x18000b06a  mov     [r8], cx
0x18000b06e  add     r9w, bp
0x18000b072  add     r8, r15
0x18000b075  cmp     r9w, di
0x18000b079  jb      short loc_18000B000
0x18000b07b  xor     ecx, ecx
0x18000b07d  mov     [r8], cx
0x18000b081  mov     eax, esi
0x18000b083  add     rsp, 20h
0x18000b087  pop     r15
0x18000b089  pop     r14
0x18000b08b  pop     r12
0x18000b08d  pop     rdi
0x18000b08e  pop     rsi
0x18000b08f  pop     rbp
0x18000b090  pop     rbx
0x18000b091  retn
```
