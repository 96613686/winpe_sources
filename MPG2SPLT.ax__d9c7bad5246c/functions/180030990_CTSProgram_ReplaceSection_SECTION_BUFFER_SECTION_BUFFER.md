# CTSProgram::ReplaceSection_(SECTION_BUFFER *,SECTION_BUFFER *)

- ea: `0x180030990`
- end: `0x180030c16`
- name: `?ReplaceSection_@CTSProgram@@AEAAJPEAUSECTION_BUFFER@@0@Z`
- size: `646`
- prototype: `__int64 __fastcall(CTSProgram *__hidden this, struct SECTION_BUFFER *, struct SECTION_BUFFER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18002fd00`

## callees

- `0x18002ea84`
- `0x18002f344`
- `0x18003042c`
- `0x1800305a4`
- `0x180030668`
- `0x180030990`
- `0x180030d08`
- `0x180030f74`

## pseudocode

```c
__int64 __fastcall CTSProgram::ReplaceSection_(CTSProgram *this, struct SECTION_BUFFER *a2, struct SECTION_BUFFER *a3)
{
  int v6; // eax
  __int64 result; // rax
  int New; // esi
  char *v9; // r12
  char *v10; // rbp
  struct SINGULAR_STREAM *v11; // rbx
  unsigned __int8 *v12; // r15
  unsigned __int8 *v13; // rbp
  struct SINGULAR_STREAM *v14; // rdx
  struct SINGULAR_STREAM **v15; // rcx
  struct SINGULAR_STREAM *v16; // rax
  struct SINGULAR_STREAM *v17; // rbx
  struct SINGULAR_STREAM **v18; // rcx
  struct SINGULAR_STREAM *v19; // rax
  struct SINGULAR_STREAM *v20; // [rsp+70h] [rbp+8h] BYREF

  v6 = HIBYTE(*(unsigned __int16 *)((char *)a2 + 11)) | ((unsigned __int8)*(_WORD *)((char *)a2 + 11) << 8);
  v20 = 0;
  if ( v6 != *((_DWORD *)this + 6) )
    return 2147549183LL;
  result = CTSProgram::CheckPCRPID_(this, a2);
  New = result;
  if ( (int)result >= 0 )
  {
    v9 = (char *)a3
       + (HIBYTE(*(unsigned __int16 *)((char *)a3 + 9)) | ((*(unsigned __int16 *)((_BYTE *)a3 + 9) & 0xFu) << 8))
       + 7;
    v10 = (char *)a3
        + (((unsigned __int64)*((unsigned __int16 *)a3 + 9) >> 8) | ((*((unsigned __int16 *)a3 + 9) & 0xFu) << 8))
        + 20;
    if ( v10 )
    {
      while ( 1 )
      {
        New = TGenericMap<unsigned __int64,unsigned long,0,5,19>::Remove(
                (char *)this + 104,
                HIBYTE(*(unsigned __int16 *)(v10 + 1)) | ((unsigned __int8)(*(_WORD *)(v10 + 1) & 0x1F) << 8),
                &v20);
        if ( New >= 0 )
        {
          v11 = v20;
          New = TGenericMap<unsigned __int64,unsigned long,0,5,19>::Store(
                  (char *)this + 528,
                  v20,
                  *((unsigned int *)v20 + 4));
          if ( New < 0 )
            break;
        }
        v10 += ((unsigned __int8)v10[4] | (unsigned __int64)((*(_WORD *)(v10 + 3) & 0xFu) << 8)) + 5;
        if ( v10 >= v9 || !v10 )
          goto LABEL_9;
      }
LABEL_19:
      CTSContentManager::UnregisterKnownStream(*((CTSContentManager **)this + 4), v11);
LABEL_20:
      v15 = (struct SINGULAR_STREAM **)(*((_QWORD *)this + 4) + 72LL);
      v16 = *v15;
      *(_QWORD *)v11 = *v15;
      *((_QWORD *)v11 + 1) = v15;
      *((_QWORD *)v16 + 1) = v11;
      *v15 = v11;
    }
    else
    {
LABEL_9:
      v12 = (unsigned __int8 *)a2
          + (HIBYTE(*(unsigned __int16 *)((char *)a2 + 9)) | ((*(unsigned __int16 *)((_BYTE *)a2 + 9) & 0xFu) << 8))
          + 7;
      v13 = (unsigned __int8 *)a2
          + (((unsigned __int64)*((unsigned __int16 *)a2 + 9) >> 8) | ((*((unsigned __int16 *)a2 + 9) & 0xFu) << 8))
          + 20;
      if ( v13 )
      {
        do
        {
          if ( (int)TGenericMap<unsigned __int64,unsigned long,0,5,19>::Remove(
                      (char *)this + 528,
                      HIBYTE(*(unsigned __int16 *)(v13 + 1)) | ((unsigned __int8)(*(_WORD *)(v13 + 1) & 0x1F) << 8),
                      &v20) >= 0 )
          {
            v11 = v20;
          }
          else
          {
            New = CTSContentManager::GetNew(*((CTSContentManager **)this + 4), &v20);
            if ( New < 0 )
              break;
            v11 = v20;
            v14 = v20;
            *((_DWORD *)v20 + 4) = HIBYTE(*(unsigned __int16 *)(v13 + 1)) | ((*(_WORD *)(v13 + 1) & 0x1F) << 8);
            *((_DWORD *)v14 + 5) = *v13;
            *((_DWORD *)v14 + 6) = *((_DWORD *)this + 6);
            New = CTSContentManager::RegisterKnownStream(*((CTSContentManager **)this + 4), v14);
            if ( New < 0 )
              goto LABEL_20;
          }
          New = TGenericMap<unsigned __int64,unsigned long,0,5,19>::Store(
                  (char *)this + 104,
                  v11,
                  *((unsigned int *)v11 + 4));
          if ( New < 0 )
            goto LABEL_19;
          v13 += (v13[4] | (unsigned __int64)((*(_WORD *)(v13 + 3) & 0xFu) << 8)) + 5;
        }
        while ( v13 < v12 && v13 );
      }
    }
    while ( *((CTSProgram **)this + 112) != (CTSProgram *)((char *)this + 896) )
    {
      TGenericMap<unsigned __int64,unsigned long,0,5,19>::RemoveFirst((char *)this + 528, &v20);
      v17 = v20;
      CTSContentManager::UnregisterKnownStream(*((CTSContentManager **)this + 4), v20);
      v18 = (struct SINGULAR_STREAM **)(*((_QWORD *)this + 4) + 72LL);
      v19 = *v18;
      *(_QWORD *)v17 = *v18;
      *((_QWORD *)v17 + 1) = v18;
      *((_QWORD *)v19 + 1) = v17;
      *v18 = v17;
    }
    return (unsigned int)New;
  }
  return result;
}

```

## disassembly

```asm
0x180030990  push    rbx
0x180030992  push    rbp
0x180030993  push    rsi
0x180030994  push    rdi
0x180030995  push    r12
0x180030997  push    r13
0x180030999  push    r14
0x18003099b  push    r15
0x18003099d  sub     rsp, 28h
0x1800309a1  movzx   r9d, word ptr [rdx+0Bh]
0x1800309a6  mov     rbx, r8
0x1800309a9  movzx   eax, r9b
0x1800309ad  mov     r14, rdx
0x1800309b0  shl     eax, 8
0x1800309b3  mov     rdi, rcx
0x1800309b6  shr     r9d, 8
0x1800309ba  or      eax, r9d
0x1800309bd  mov     [rsp+68h+arg_0], 0
0x1800309c6  cmp     eax, [rcx+18h]
0x1800309c9  jz      short loc_1800309D5
0x1800309cb  mov     eax, 8000FFFFh
0x1800309d0  jmp     loc_180030C05
0x1800309d5  call    ?CheckPCRPID_@CTSProgram@@AEAAJPEAUSECTION_BUFFER@@@Z; CTSProgram::CheckPCRPID_(SECTION_BUFFER *)
0x1800309da  mov     esi, eax
0x1800309dc  test    eax, eax
0x1800309de  js      loc_180030C05
0x1800309e4  movzx   eax, word ptr [rbx+9]
0x1800309e8  mov     r13d, 0Fh
0x1800309ee  movzx   ecx, word ptr [rbx+12h]
0x1800309f2  mov     r12d, eax
0x1800309f5  and     r12d, r13d
0x1800309f8  shr     eax, 8
0x1800309fb  shl     r12d, 8
0x1800309ff  mov     ebp, ecx
0x180030a01  or      r12d, eax
0x180030a04  shr     rcx, 8
0x180030a08  and     ebp, r13d
0x180030a0b  add     r12d, 3
0x180030a0f  shl     ebp, 8
0x180030a12  add     r12, 4
0x180030a16  or      rbp, rcx
0x180030a19  add     r12, rbx
0x180030a1c  add     rbp, 14h
0x180030a20  add     rbp, rbx
0x180030a23  jz      short loc_180030A93
0x180030a25  movzx   eax, word ptr [rbp+1]
0x180030a29  lea     r8, [rsp+68h+arg_0]
0x180030a2e  mov     edx, eax
0x180030a30  lea     rcx, [rdi+68h]
0x180030a34  and     edx, 1Fh
0x180030a37  shr     eax, 8
0x180030a3a  shl     edx, 8
0x180030a3d  or      edx, eax
0x180030a3f  call    ?Remove@?$TGenericMap@_KK$0A@$04$0BD@@@QEAAJKPEA_K@Z; TGenericMap<unsigned __int64,ulong,0,5,19>::Remove(ulong,unsigned __int64 *)
0x180030a44  mov     esi, eax
0x180030a46  test    eax, eax
0x180030a48  js      short loc_180030A6C
0x180030a4a  mov     rbx, [rsp+68h+arg_0]
0x180030a4f  lea     rcx, [rdi+210h]
0x180030a56  mov     rdx, rbx
0x180030a59  mov     r8d, [rbx+10h]
0x180030a5d  call    ?Store@?$TGenericMap@_KK$0A@$04$0BD@@@QEAAJ_KK@Z; TGenericMap<unsigned __int64,ulong,0,5,19>::Store(unsigned __int64,ulong)
0x180030a62  mov     esi, eax
0x180030a64  test    eax, eax
0x180030a66  js      loc_180030B94
0x180030a6c  movzx   eax, word ptr [rbp+3]
0x180030a70  and     ax, r13w
0x180030a74  shl     ax, 8
0x180030a78  movzx   ecx, ax
0x180030a7b  movzx   eax, byte ptr [rbp+4]
0x180030a7f  add     rbp, 5
0x180030a83  or      rcx, rax
0x180030a86  add     rbp, rcx
0x180030a89  cmp     rbp, r12
0x180030a8c  jnb     short loc_180030A93
0x180030a8e  test    rbp, rbp
0x180030a91  jnz     short loc_180030A25
0x180030a93  movzx   eax, word ptr [r14+9]
0x180030a98  movzx   edx, word ptr [r14+12h]
0x180030a9d  mov     r15d, eax
0x180030aa0  and     r15d, r13d
0x180030aa3  shr     eax, 8
0x180030aa6  shl     r15d, 8
0x180030aaa  mov     ebp, edx
0x180030aac  or      r15d, eax
0x180030aaf  shr     rdx, 8
0x180030ab3  and     ebp, r13d
0x180030ab6  add     r15d, 3
0x180030aba  shl     ebp, 8
0x180030abd  add     r15, 4
0x180030ac1  or      rbp, rdx
0x180030ac4  add     r15, r14
0x180030ac7  add     rbp, 14h
0x180030acb  add     rbp, r14
0x180030ace  jz      loc_180030BB9
0x180030ad4  movzx   eax, word ptr [rbp+1]
0x180030ad8  lea     r8, [rsp+68h+arg_0]
0x180030add  mov     edx, eax
0x180030adf  lea     rcx, [rdi+210h]
0x180030ae6  and     edx, 1Fh
0x180030ae9  shr     eax, 8
0x180030aec  shl     edx, 8
0x180030aef  or      edx, eax
0x180030af1  call    ?Remove@?$TGenericMap@_KK$0A@$04$0BD@@@QEAAJKPEA_K@Z; TGenericMap<unsigned __int64,ulong,0,5,19>::Remove(ulong,unsigned __int64 *)
0x180030af6  test    eax, eax
0x180030af8  jns     short loc_180030B4C
0x180030afa  mov     rcx, [rdi+20h]; this
0x180030afe  lea     rdx, [rsp+68h+arg_0]; struct SINGULAR_STREAM **
0x180030b03  call    ?GetNew@CTSContentManager@@QEAAJPEAPEAUSINGULAR_STREAM@@@Z; CTSContentManager::GetNew(SINGULAR_STREAM * *)
0x180030b08  mov     esi, eax
0x180030b0a  test    eax, eax
0x180030b0c  js      loc_180030BB9
0x180030b12  movzx   eax, word ptr [rbp+1]
0x180030b16  mov     rbx, [rsp+68h+arg_0]
0x180030b1b  mov     ecx, eax
0x180030b1d  and     ecx, 1Fh
0x180030b20  shr     eax, 8
0x180030b23  shl     ecx, 8
0x180030b26  mov     rdx, rbx; struct SINGULAR_STREAM *
0x180030b29  or      ecx, eax
0x180030b2b  mov     [rbx+10h], ecx
0x180030b2e  movzx   eax, byte ptr [rbp+0]
0x180030b32  mov     [rbx+14h], eax
0x180030b35  mov     eax, [rdi+18h]
0x180030b38  mov     [rbx+18h], eax
0x180030b3b  mov     rcx, [rdi+20h]; this
0x180030b3f  call    ?RegisterKnownStream@CTSContentManager@@QEAAJPEAUSINGULAR_STREAM@@@Z; CTSContentManager::RegisterKnownStream(SINGULAR_STREAM *)
0x180030b44  mov     esi, eax
0x180030b46  test    eax, eax
0x180030b48  js      short loc_180030BA0
0x180030b4a  jmp     short loc_180030B51
0x180030b4c  mov     rbx, [rsp+68h+arg_0]
0x180030b51  mov     r8d, [rbx+10h]
0x180030b55  lea     rcx, [rdi+68h]
0x180030b59  mov     rdx, rbx
0x180030b5c  call    ?Store@?$TGenericMap@_KK$0A@$04$0BD@@@QEAAJ_KK@Z; TGenericMap<unsigned __int64,ulong,0,5,19>::Store(unsigned __int64,ulong)
0x180030b61  mov     esi, eax
0x180030b63  test    eax, eax
0x180030b65  js      short loc_180030B94
0x180030b67  movzx   eax, word ptr [rbp+3]
0x180030b6b  and     ax, r13w
0x180030b6f  shl     ax, 8
0x180030b73  movzx   ecx, ax
0x180030b76  movzx   eax, byte ptr [rbp+4]
0x180030b7a  add     rbp, 5
0x180030b7e  or      rcx, rax
0x180030b81  add     rbp, rcx
0x180030b84  cmp     rbp, r15
0x180030b87  jnb     short loc_180030BB9
0x180030b89  test    rbp, rbp
0x180030b8c  jnz     loc_180030AD4
0x180030b92  jmp     short loc_180030BB9
0x180030b94  mov     rcx, [rdi+20h]; this
0x180030b98  mov     rdx, rbx; struct SINGULAR_STREAM *
0x180030b9b  call    ?UnregisterKnownStream@CTSContentManager@@QEAAJPEAUSINGULAR_STREAM@@@Z; CTSContentManager::UnregisterKnownStream(SINGULAR_STREAM *)
0x180030ba0  mov     rcx, [rdi+20h]
0x180030ba4  add     rcx, 48h ; 'H'
0x180030ba8  mov     rax, [rcx]
0x180030bab  mov     [rbx], rax
0x180030bae  mov     [rbx+8], rcx
0x180030bb2  mov     [rax+8], rbx
0x180030bb6  mov     [rcx], rbx
0x180030bb9  lea     rbp, [rdi+380h]
0x180030bc0  cmp     [rbp+0], rbp
0x180030bc4  jz      short loc_180030C03
0x180030bc6  lea     rdx, [rsp+68h+arg_0]
0x180030bcb  lea     rcx, [rdi+210h]
0x180030bd2  call    ?RemoveFirst@?$TGenericMap@_KK$0A@$04$0BD@@@QEAAJPEA_K@Z; TGenericMap<unsigned __int64,ulong,0,5,19>::RemoveFirst(unsigned __int64 *)
0x180030bd7  mov     rbx, [rsp+68h+arg_0]
0x180030bdc  mov     rcx, [rdi+20h]; this
0x180030be0  mov     rdx, rbx; struct SINGULAR_STREAM *
0x180030be3  call    ?UnregisterKnownStream@CTSContentManager@@QEAAJPEAUSINGULAR_STREAM@@@Z; CTSContentManager::UnregisterKnownStream(SINGULAR_STREAM *)
0x180030be8  mov     rcx, [rdi+20h]
0x180030bec  add     rcx, 48h ; 'H'
0x180030bf0  mov     rax, [rcx]
0x180030bf3  mov     [rbx], rax
0x180030bf6  mov     [rbx+8], rcx
0x180030bfa  mov     [rax+8], rbx
0x180030bfe  mov     [rcx], rbx
0x180030c01  jmp     short loc_180030BC0
0x180030c03  mov     eax, esi
0x180030c05  add     rsp, 28h
0x180030c09  pop     r15
0x180030c0b  pop     r14
0x180030c0d  pop     r13
0x180030c0f  pop     r12
0x180030c11  pop     rdi
0x180030c12  pop     rsi
0x180030c13  pop     rbp
0x180030c14  pop     rbx
0x180030c15  retn
```
