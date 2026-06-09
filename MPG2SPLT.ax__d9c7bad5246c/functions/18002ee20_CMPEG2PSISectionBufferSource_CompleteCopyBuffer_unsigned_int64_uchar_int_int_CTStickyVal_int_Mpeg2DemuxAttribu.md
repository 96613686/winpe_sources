# CMPEG2PSISectionBufferSource::CompleteCopyBuffer(unsigned __int64,uchar *,int,int,CTStickyVal<int> *,Mpeg2DemuxAttributes::CAttributeList *)

- ea: `0x18002ee20`
- end: `0x18002eef7`
- name: `?CompleteCopyBuffer@CMPEG2PSISectionBufferSource@@UEAAJ_KPEAEHHPEAV?$CTStickyVal@H@@PEAVCAttributeList@Mpeg2DemuxAttributes@@@Z`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002ee20`
- `0x18002f9e0`
- `0x180030524`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CMPEG2PSISectionBufferSource::CompleteCopyBuffer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7)
{
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // r8
  int v14; // ebp
  __int64 v15; // rcx
  _QWORD *v16; // rax
  _QWORD v17[7]; // [rsp+20h] [rbp-38h] BYREF

  v17[0] = 0;
  if ( a7 && *(int *)(a7 + 160) > 2 )
    return 2147549183LL;
  *(_DWORD *)(a2 + 16) = *(unsigned __int8 *)(a2 + 30);
  v10 = (*(unsigned __int8 *)(a2 + 29) >> 1) & 0x1F;
  a7 = a2;
  *(_DWORD *)(a2 + 20) = v10;
  CMPEG2PSISectionBufferSource::InsertNewSection_(a1, a2, v17);
  v12 = v17[0];
  if ( v17[0] )
    v13 = v17[0] + 16LL;
  else
    v13 = 0;
  v14 = (***(__int64 (__fastcall ****)(_QWORD, __int64, __int64))(a1 + 32))(*(_QWORD *)(a1 + 32), v11 + 16, v13);
  if ( v14 < 0 )
  {
    v15 = *(_QWORD *)a2;
    v16 = *(_QWORD **)(a2 + 8);
    *v16 = *(_QWORD *)a2;
    *(_QWORD *)(v15 + 8) = v16;
    CMPEG2PSISectionBufferSource::ReleaseSectionBuffer(a1, a2);
    if ( v12 )
      CMPEG2PSISectionBufferSource::InsertNewSection_(a1, v12, &a7);
  }
  else if ( v12 )
  {
    CMPEG2PSISectionBufferSource::ReleaseSectionBuffer(a1, v12);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002ee20  push    rbx
0x18002ee22  push    rbp
0x18002ee23  push    rsi
0x18002ee24  push    rdi
0x18002ee25  sub     rsp, 38h
0x18002ee29  mov     rax, [rsp+58h+arg_30]
0x18002ee31  mov     rdi, rdx
0x18002ee34  mov     [rsp+58h+var_38], 0
0x18002ee3d  mov     rsi, rcx
0x18002ee40  test    rax, rax
0x18002ee43  jz      short loc_18002EE58
0x18002ee45  cmp     dword ptr [rax+0A0h], 2
0x18002ee4c  jle     short loc_18002EE58
0x18002ee4e  mov     eax, 8000FFFFh
0x18002ee53  jmp     loc_18002EEEE
0x18002ee58  movzx   eax, byte ptr [rdx+1Eh]
0x18002ee5c  lea     r8, [rsp+58h+var_38]
0x18002ee61  mov     [rdx+10h], eax
0x18002ee64  movzx   eax, byte ptr [rdx+1Dh]
0x18002ee68  shr     eax, 1
0x18002ee6a  and     eax, 1Fh
0x18002ee6d  mov     [rsp+58h+arg_30], rdi
0x18002ee75  mov     [rdx+14h], eax
0x18002ee78  call    ?InsertNewSection_@CMPEG2PSISectionBufferSource@@AEAAXPEAU?$LIST_ENTRY_CONTAINER@USECTION_BUFFER@@@@PEAPEAU2@@Z; CMPEG2PSISectionBufferSource::InsertNewSection_(LIST_ENTRY_CONTAINER<SECTION_BUFFER> *,LIST_ENTRY_CONTAINER<SECTION_BUFFER> * *)
0x18002ee7d  mov     rcx, [rsi+20h]
0x18002ee81  mov     rbx, [rsp+58h+var_38]
0x18002ee86  mov     rax, [rcx]
0x18002ee89  test    rbx, rbx
0x18002ee8c  jz      short loc_18002EE94
0x18002ee8e  lea     r8, [rbx+10h]
0x18002ee92  jmp     short loc_18002EE97
0x18002ee94  xor     r8d, r8d
0x18002ee97  mov     rax, [rax]
0x18002ee9a  add     rdx, 10h
0x18002ee9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eea3  mov     ebp, eax
0x18002eea5  test    eax, eax
0x18002eea7  js      short loc_18002EEBB
0x18002eea9  test    rbx, rbx
0x18002eeac  jz      short loc_18002EEEC
0x18002eeae  mov     rdx, rbx
0x18002eeb1  mov     rcx, rsi
0x18002eeb4  call    ?ReleaseSectionBuffer@CMPEG2PSISectionBufferSource@@QEAAJPEAU?$LIST_ENTRY_CONTAINER@USECTION_BUFFER@@@@@Z; CMPEG2PSISectionBufferSource::ReleaseSectionBuffer(LIST_ENTRY_CONTAINER<SECTION_BUFFER> *)
0x18002eeb9  jmp     short loc_18002EEEC
0x18002eebb  mov     rcx, [rdi]
0x18002eebe  mov     rdx, rdi
0x18002eec1  mov     rax, [rdi+8]
0x18002eec5  mov     [rax], rcx
0x18002eec8  mov     [rcx+8], rax
0x18002eecc  mov     rcx, rsi
0x18002eecf  call    ?ReleaseSectionBuffer@CMPEG2PSISectionBufferSource@@QEAAJPEAU?$LIST_ENTRY_CONTAINER@USECTION_BUFFER@@@@@Z; CMPEG2PSISectionBufferSource::ReleaseSectionBuffer(LIST_ENTRY_CONTAINER<SECTION_BUFFER> *)
0x18002eed4  test    rbx, rbx
0x18002eed7  jz      short loc_18002EEEC
0x18002eed9  lea     r8, [rsp+58h+arg_30]
0x18002eee1  mov     rdx, rbx
0x18002eee4  mov     rcx, rsi
0x18002eee7  call    ?InsertNewSection_@CMPEG2PSISectionBufferSource@@AEAAXPEAU?$LIST_ENTRY_CONTAINER@USECTION_BUFFER@@@@PEAPEAU2@@Z; CMPEG2PSISectionBufferSource::InsertNewSection_(LIST_ENTRY_CONTAINER<SECTION_BUFFER> *,LIST_ENTRY_CONTAINER<SECTION_BUFFER> * *)
0x18002eeec  mov     eax, ebp
0x18002eeee  add     rsp, 38h
0x18002eef2  pop     rdi
0x18002eef3  pop     rsi
0x18002eef4  pop     rbp
0x18002eef5  pop     rbx
0x18002eef6  retn
```
