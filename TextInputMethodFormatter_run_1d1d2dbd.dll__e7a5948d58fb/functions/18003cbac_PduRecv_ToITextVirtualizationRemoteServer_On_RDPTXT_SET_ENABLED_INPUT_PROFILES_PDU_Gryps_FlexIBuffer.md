# PduRecv_ToITextVirtualizationRemoteServer::On_RDPTXT_SET_ENABLED_INPUT_PROFILES_PDU(Gryps::FlexIBuffer *)

- ea: `0x18003cbac`
- end: `0x18003cee2`
- name: `?On_RDPTXT_SET_ENABLED_INPUT_PROFILES_PDU@PduRecv_ToITextVirtualizationRemoteServer@@QEAAJPEAVFlexIBuffer@Gryps@@@Z`
- size: `822`
- prototype: `__int64 __fastcall(PduRecv_ToITextVirtualizationRemoteServer *__hidden this, struct Gryps::FlexIBuffer *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18003c6f0`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x180002db8`
- `0x18000428c`
- `0x180015a44`
- `0x180038c0c`
- `0x180038cc4`
- `0x180038d7c`
- `0x180038e34`
- `0x18003c34c`
- `0x18003c538`
- `0x18003c65c`
- `0x18003cbac`
- `0x180058010`

## import_xrefs

- `CoreMessaging!MsgBlobCreateShared` at `0x18003ce7c`
- `CoreMessaging!MsgBlobCreateShared` at `0x18003ce7c`
- `CoreMessaging!MsgRelease` at `0x18003ce9c`
- `CoreMessaging!MsgRelease` at `0x18003ce9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall PduRecv_ToITextVirtualizationRemoteServer::On_RDPTXT_SET_ENABLED_INPUT_PROFILES_PDU(
        PduRecv_ToITextVirtualizationRemoteServer *this,
        struct Gryps::FlexIBuffer *a2)
{
  unsigned int v4; // esi
  unsigned int i; // r15d
  __int64 j; // rdi
  __int64 k; // rdi
  __int64 m; // rdi
  unsigned int v9; // edi
  unsigned int v10; // r14d
  unsigned int v11; // ecx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h]
  __int128 v21; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h]
  _WORD v23[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v24; // [rsp+74h] [rbp-8Ch] BYREF
  __int128 v25; // [rsp+84h] [rbp-7Ch] BYREF
  __int128 v26; // [rsp+94h] [rbp-6Ch] BYREF
  int v27; // [rsp+A4h] [rbp-5Ch] BYREF
  int v28; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v29; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v30; // [rsp+B0h] [rbp-50h]
  unsigned int v31; // [rsp+B4h] [rbp-4Ch]
  unsigned int v32; // [rsp+B8h] [rbp-48h]
  __int64 v33; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v34; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v35[64]; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v36; // [rsp+120h] [rbp+20h]
  _BYTE v37[32]; // [rsp+130h] [rbp+30h] BYREF

  v18 = 0;
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000) != 0
    && (qword_180082098 & 0x400000) == qword_180082098 )
  {
    tlgWriteTransfer_EventWriteTransfer(&dword_180082080, &unk_180075D35, 0, 0, 2, v37);
  }
  memset_0(v23, 0, 0x58u);
  v19 = 0;
  v20 = 0;
  v17 = 0;
  Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v17);
  v4 = 0;
  for ( i = v17; v4 < i; ++v4 )
  {
    Gryps::FlexIBuffer::extractLE<short>((__int64)a2, v23);
    for ( j = 0; j != 16; ++j )
      Gryps::FlexIBuffer::extractLE<unsigned char>(a2, (char *)&v24 + j);
    for ( k = 0; k != 16; ++k )
      Gryps::FlexIBuffer::extractLE<unsigned char>(a2, (char *)&v25 + k);
    for ( m = 0; m != 16; ++m )
      Gryps::FlexIBuffer::extractLE<unsigned char>(a2, (char *)&v26 + m);
    Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v27);
    Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v28);
    Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v29);
    v17 = 0;
    Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v17);
    v9 = v17;
    v30 = v17;
    v17 = 0;
    Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v17);
    v10 = v17;
    v31 = v17;
    v17 = 0;
    Gryps::FlexIBuffer::extractLE<unsigned int>((__int64)a2, &v17);
    v11 = v17;
    v32 = v17;
    if ( *((_DWORD *)this + 8) > 1u || (*((_BYTE *)this + 36) & 2) != 0 )
    {
      Gryps::FlexIBuffer::extractLE<unsigned __int64>((__int64)a2, &v33);
      v11 = v32;
      v10 = v31;
      v9 = v30;
    }
    *(_DWORD *)v35 = v23[0];
    *(_OWORD *)&v35[4] = v24;
    *(_OWORD *)&v35[36] = v25;
    *(_OWORD *)&v35[20] = v26;
    *(_DWORD *)&v35[52] = v27;
    *(_DWORD *)&v35[56] = v28;
    *(_QWORD *)&v34 = v9;
    *(_DWORD *)&v35[60] = v10;
    v36 = __PAIR64__(v29, v11);
    *((_QWORD *)&v34 + 1) = v33;
    v12 = *((_QWORD *)&v19 + 1);
    if ( *((_QWORD *)&v19 + 1) == v20 )
    {
      std::vector<CoreInputProfile>::_Emplace_reallocate<CoreInputProfile const &>(&v19, *((_QWORD *)&v19 + 1), &v34);
    }
    else
    {
      **((_OWORD **)&v19 + 1) = v34;
      *(_OWORD *)(v12 + 16) = *(_OWORD *)v35;
      *(_OWORD *)(v12 + 32) = *(_OWORD *)&v35[16];
      *(_OWORD *)(v12 + 48) = *(_OWORD *)&v35[32];
      *(_OWORD *)(v12 + 64) = *(_OWORD *)&v35[48];
      *(_QWORD *)(v12 + 80) = v36;
      *((_QWORD *)&v19 + 1) += 88LL;
    }
  }
  v21 = 0;
  v22 = 0;
  std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(&v21);
  *(_DWORD *)v21 = i;
  std::vector<char>::_Insert_counted_range<char const *>(&v21, *((_QWORD *)&v21 + 1), v19, (int)(88 * i));
  MsgBlobCreateShared(v21, 88 * i + 4, &v18);
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 3) + 32LL))(*((_QWORD *)this + 3), v18);
  MsgRelease(v18, v13, v14, v15);
  std::vector<char>::~vector<char>(&v21);
  std::vector<CoreInputProfile>::~vector<CoreInputProfile>(&v19);
  return 0;
}

```

## disassembly

```asm
0x18003cbac  mov     [rsp-8+arg_10], rbx
0x18003cbb1  mov     [rsp-8+arg_18], rsi
0x18003cbb6  push    rbp
0x18003cbb7  push    rdi
0x18003cbb8  push    r13
0x18003cbba  push    r14
0x18003cbbc  push    r15
0x18003cbbe  lea     rbp, [rsp-60h]
0x18003cbc3  sub     rsp, 160h
0x18003cbca  mov     rax, cs:__security_cookie
0x18003cbd1  xor     rax, rsp
0x18003cbd4  mov     [rbp+80h+var_30], rax
0x18003cbd8  mov     rbx, rdx
0x18003cbdb  mov     r13, rcx
0x18003cbde  mov     [rsp+180h+var_148], 0
0x18003cbe7  mov     eax, cs:dword_180082080
0x18003cbed  cmp     eax, 5
0x18003cbf0  jbe     short loc_18003CC3F
0x18003cbf2  mov     rcx, cs:qword_180082098
0x18003cbf9  mov     rax, cs:qword_180082090
0x18003cc00  mov     edx, 400000h
0x18003cc05  test    rdx, rax
0x18003cc08  jz      short loc_18003CC3F
0x18003cc0a  mov     rax, rcx
0x18003cc0d  and     rax, rdx
0x18003cc10  cmp     rax, rcx
0x18003cc13  jnz     short loc_18003CC3F
0x18003cc15  lea     rax, [rbp+80h+var_50]
0x18003cc19  mov     [rsp+180h+var_158], rax
0x18003cc1e  mov     [rsp+180h+var_160], 2
0x18003cc26  xor     r9d, r9d
0x18003cc29  xor     r8d, r8d
0x18003cc2c  lea     rdx, unk_180075D35
0x18003cc33  lea     rcx, dword_180082080
0x18003cc3a  call    _tlgWriteTransfer_EventWriteTransfer
0x18003cc3f  xor     edx, edx; Val
0x18003cc41  lea     r8d, [rdx+58h]; Size
0x18003cc45  lea     rcx, [rsp+180h+var_110]; void *
0x18003cc4a  call    memset_0
0x18003cc4f  xorps   xmm0, xmm0
0x18003cc52  movdqu  [rsp+180h+var_140], xmm0
0x18003cc58  mov     [rsp+180h+var_130], 0
0x18003cc61  mov     [rsp+180h+var_150], 0
0x18003cc69  lea     rdx, [rsp+180h+var_150]
0x18003cc6e  mov     rcx, rbx
0x18003cc71  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003cc76  xor     esi, esi
0x18003cc78  mov     r15d, [rsp+180h+var_150]
0x18003cc7d  test    r15d, r15d
0x18003cc80  jz      loc_18003CE30
0x18003cc86  lea     rdx, [rsp+180h+var_110]
0x18003cc8b  mov     rcx, rbx
0x18003cc8e  call    ??$extractLE@F@FlexIBuffer@Gryps@@QEAAXAEAF@Z; Gryps::FlexIBuffer::extractLE<short>(short &)
0x18003cc93  xor     edi, edi
0x18003cc95  lea     rdx, [rsp+180h+var_10C]
0x18003cc9a  add     rdx, rdi
0x18003cc9d  mov     rcx, rbx
0x18003cca0  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x18003cca5  inc     rdi
0x18003cca8  cmp     rdi, 10h
0x18003ccac  jnz     short loc_18003CC95
0x18003ccae  xor     edi, edi
0x18003ccb0  lea     rdx, [rbp+80h+var_FC]
0x18003ccb4  add     rdx, rdi
0x18003ccb7  mov     rcx, rbx
0x18003ccba  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x18003ccbf  inc     rdi
0x18003ccc2  cmp     rdi, 10h
0x18003ccc6  jnz     short loc_18003CCB0
0x18003ccc8  xor     edi, edi
0x18003ccca  lea     rdx, [rbp+80h+var_EC]
0x18003ccce  add     rdx, rdi
0x18003ccd1  mov     rcx, rbx
0x18003ccd4  call    ??$extractLE@E@FlexIBuffer@Gryps@@QEAAXAEAE@Z; Gryps::FlexIBuffer::extractLE<uchar>(uchar &)
0x18003ccd9  inc     rdi
0x18003ccdc  cmp     rdi, 10h
0x18003cce0  jnz     short loc_18003CCCA
0x18003cce2  lea     rdx, [rbp+80h+var_DC]
0x18003cce6  mov     rcx, rbx
0x18003cce9  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003ccee  lea     rdx, [rbp+80h+var_D8]
0x18003ccf2  mov     rcx, rbx
0x18003ccf5  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003ccfa  lea     rdx, [rbp+80h+var_D4]
0x18003ccfe  mov     rcx, rbx
0x18003cd01  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003cd06  mov     [rsp+180h+var_150], 0
0x18003cd0e  lea     rdx, [rsp+180h+var_150]
0x18003cd13  mov     rcx, rbx
0x18003cd16  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003cd1b  mov     edi, [rsp+180h+var_150]
0x18003cd1f  mov     [rbp+80h+var_D0], edi
0x18003cd22  mov     [rsp+180h+var_150], 0
0x18003cd2a  lea     rdx, [rsp+180h+var_150]
0x18003cd2f  mov     rcx, rbx
0x18003cd32  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003cd37  mov     r14d, [rsp+180h+var_150]
0x18003cd3c  mov     [rbp+80h+var_CC], r14d
0x18003cd40  mov     [rsp+180h+var_150], 0
0x18003cd48  lea     rdx, [rsp+180h+var_150]
0x18003cd4d  mov     rcx, rbx
0x18003cd50  call    ??$extractLE@I@FlexIBuffer@Gryps@@QEAAXAEAI@Z; Gryps::FlexIBuffer::extractLE<uint>(uint &)
0x18003cd55  mov     ecx, [rsp+180h+var_150]
0x18003cd59  mov     [rbp+80h+var_C8], ecx
0x18003cd5c  cmp     dword ptr [r13+20h], 1
0x18003cd61  ja      short loc_18003CD6A
0x18003cd63  test    byte ptr [r13+24h], 2
0x18003cd68  jz      short loc_18003CD80
0x18003cd6a  lea     rdx, [rbp+80h+var_C0]
0x18003cd6e  mov     rcx, rbx
0x18003cd71  call    ??$extractLE@_K@FlexIBuffer@Gryps@@QEAAXAEA_K@Z; Gryps::FlexIBuffer::extractLE<unsigned __int64>(unsigned __int64 &)
0x18003cd76  mov     ecx, [rbp+80h+var_C8]
0x18003cd79  mov     r14d, [rbp+80h+var_CC]
0x18003cd7d  mov     edi, [rbp+80h+var_D0]
0x18003cd80  xor     eax, eax
0x18003cd82  mov     dword ptr [rbp+80h+var_B0+4], eax
0x18003cd85  mov     word ptr [rbp+80h+var_A0+2], ax
0x18003cd89  movzx   eax, [rsp+180h+var_110]
0x18003cd8e  mov     word ptr [rbp+80h+var_A0], ax
0x18003cd92  movups  xmm0, [rsp+180h+var_10C]
0x18003cd97  movdqu  [rbp+80h+var_A0+4], xmm0
0x18003cd9c  movups  xmm1, [rbp+80h+var_FC]
0x18003cda0  movdqu  [rbp+80h+var_7C], xmm1
0x18003cda5  movups  xmm0, [rbp+80h+var_EC]
0x18003cda9  movdqu  [rbp+80h+var_8C], xmm0
0x18003cdae  mov     eax, [rbp+80h+var_DC]
0x18003cdb1  mov     [rbp+80h+var_6C], eax
0x18003cdb4  mov     eax, [rbp+80h+var_D8]
0x18003cdb7  mov     [rbp+80h+var_68], eax
0x18003cdba  mov     eax, [rbp+80h+var_D4]
0x18003cdbd  mov     dword ptr [rbp+80h+var_60+4], eax
0x18003cdc0  mov     dword ptr [rbp+80h+var_B0], edi
0x18003cdc3  mov     [rbp+80h+var_64], r14d
0x18003cdc7  mov     dword ptr [rbp+80h+var_60], ecx
0x18003cdca  mov     rax, [rbp+80h+var_C0]
0x18003cdce  mov     qword ptr [rbp+80h+var_B0+8], rax
0x18003cdd2  mov     rdx, qword ptr [rsp+180h+var_140+8]
0x18003cdd7  cmp     rdx, [rsp+180h+var_130]
0x18003cddc  jz      short loc_18003CE17
0x18003cdde  movaps  xmm0, [rbp+80h+var_B0]
0x18003cde2  movups  xmmword ptr [rdx], xmm0
0x18003cde5  movaps  xmm1, [rbp+80h+var_A0]
0x18003cde9  movups  xmmword ptr [rdx+10h], xmm1
0x18003cded  movaps  xmm0, xmmword ptr [rbp-10h]
0x18003cdf1  movups  xmmword ptr [rdx+20h], xmm0
0x18003cdf5  movaps  xmm1, [rbp+80h+var_8C+0Ch]
0x18003cdf9  movups  xmmword ptr [rdx+30h], xmm1
0x18003cdfd  movaps  xmm0, [rbp+80h+var_7C+0Ch]
0x18003ce01  movups  xmmword ptr [rdx+40h], xmm0
0x18003ce05  movsd   xmm1, [rbp+80h+var_60]
0x18003ce0a  movsd   qword ptr [rdx+50h], xmm1
0x18003ce0f  add     qword ptr [rsp+180h+var_140+8], 58h ; 'X'
0x18003ce15  jmp     short loc_18003CE25
0x18003ce17  lea     r8, [rbp+80h+var_B0]
0x18003ce1b  lea     rcx, [rsp+180h+var_140]
0x18003ce20  call    ??$_Emplace_reallocate@AEBUCoreInputProfile@@@?$vector@UCoreInputProfile@@V?$allocator@UCoreInputProfile@@@std@@@std@@AEAAPEAUCoreInputProfile@@QEAU2@AEBU2@@Z; std::vector<CoreInputProfile>::_Emplace_reallocate<CoreInputProfile const &>(CoreInputProfile * const,CoreInputProfile const &)
0x18003ce25  inc     esi
0x18003ce27  cmp     esi, r15d
0x18003ce2a  jb      loc_18003CC86
0x18003ce30  imul    ebx, r15d, 58h ; 'X'
0x18003ce34  xorps   xmm0, xmm0
0x18003ce37  movdqu  [rsp+180h+var_128], xmm0
0x18003ce3d  mov     [rsp+180h+var_118], 0
0x18003ce46  lea     rcx, [rsp+180h+var_128]
0x18003ce4b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@DV?$allocator@D@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003ce50  mov     rax, qword ptr [rsp+180h+var_128]
0x18003ce55  mov     [rax], r15d
0x18003ce58  movsxd  r9, ebx
0x18003ce5b  mov     r8, qword ptr [rsp+180h+var_140]
0x18003ce60  mov     rdx, qword ptr [rsp+180h+var_128+8]
0x18003ce65  lea     rcx, [rsp+180h+var_128]
0x18003ce6a  call    ??$_Insert_counted_range@PEBD@?$vector@DV?$allocator@D@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@D@std@@@std@@@1@PEBD_K@Z; std::vector<char>::_Insert_counted_range<char const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<char>>>,char const *,unsigned __int64)
0x18003ce6f  lea     edx, [rbx+4]
0x18003ce72  lea     r8, [rsp+180h+var_148]
0x18003ce77  mov     rcx, qword ptr [rsp+180h+var_128]
0x18003ce7c  call    cs:__imp_MsgBlobCreateShared
0x18003ce82  mov     rcx, [r13+18h]
0x18003ce86  mov     rax, [rcx]
0x18003ce89  mov     rdx, [rsp+180h+var_148]
0x18003ce8e  mov     rax, [rax+20h]
0x18003ce92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce97  mov     rcx, [rsp+180h+var_148]
0x18003ce9c  call    cs:__imp_MsgRelease
0x18003cea2  nop
0x18003cea3  lea     rcx, [rsp+180h+var_128]
0x18003cea8  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18003cead  nop
0x18003ceae  lea     rcx, [rsp+180h+var_140]
0x18003ceb3  call    ??1?$vector@UCoreInputProfile@@V?$allocator@UCoreInputProfile@@@std@@@std@@QEAA@XZ; std::vector<CoreInputProfile>::~vector<CoreInputProfile>(void)
0x18003ceb8  xor     eax, eax
0x18003ceba  mov     rcx, [rbp+80h+var_30]
0x18003cebe  xor     rcx, rsp; StackCookie
0x18003cec1  call    __security_check_cookie
0x18003cec6  lea     r11, [rsp+180h+var_20]
0x18003cece  mov     rbx, [r11+40h]
0x18003ced2  mov     rsi, [r11+48h]
0x18003ced6  mov     rsp, r11
0x18003ced9  pop     r15
0x18003cedb  pop     r14
0x18003cedd  pop     r13
0x18003cedf  pop     rdi
0x18003cee0  pop     rbp
0x18003cee1  retn
```
