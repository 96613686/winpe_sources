# PackageManager::OnPackageAddComplete(OdmlMapDataPackage *,long)

- ea: `0x18000ff9c`
- end: `0x1800101b4`
- name: `?OnPackageAddComplete@PackageManager@@AEAAXPEAVOdmlMapDataPackage@@J@Z`
- size: `536`
- prototype: `void __fastcall(PackageManager *__hidden this, struct OdmlMapDataPackage *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000fe2c`

## callees

- `0x180003f70`
- `0x18000d090`
- `0x18000d538`
- `0x18000ed18`
- `0x18000ff9c`
- `0x1800112b4`

## pseudocode

```c
void __fastcall PackageManager::OnPackageAddComplete(PackageManager *this, struct OdmlMapDataPackage *a2, int a3)
{
  struct OdmlMapDataPackage *v3; // rbx
  __int64 i; // rcx
  __int64 *v6; // rdi
  struct OdmlMapDataPackage *v7; // rsi
  __int64 v8; // r12
  __int64 j; // r14
  __int64 v10; // r8
  __int64 v11; // r10
  struct OdmlMapDataPackage **v12; // rdx
  struct OdmlMapDataPackage **v13; // r8
  _QWORD *v14; // rcx
  char *v15; // rcx
  struct OdmlMapDataPackage **v16; // rdi
  struct OdmlMapDataPackage *v17; // [rsp+58h] [rbp+10h] BYREF
  struct OdmlMapDataPackage *v18; // [rsp+68h] [rbp+20h] BYREF

  v17 = a2;
  v3 = a2;
  if ( a3 < 0 )
  {
    if ( a3 == -2080309241 || a3 == -2147023673 || a3 == -2147023661 )
    {
      if ( (unsigned int)(*((_DWORD *)a2 + 8) - 4) > 2 )
      {
        *((_DWORD *)a2 + 9) = 0;
        OdmlMapDataPackage::SetState(a2, 0);
        return;
      }
      *((_DWORD *)a2 + 9) = 1;
      *((_DWORD *)a2 + 10) = 3;
      OdmlMapDataPackage::SetState(a2, 2);
      v15 = (char *)*((_QWORD *)this + 28);
      v16 = (struct OdmlMapDataPackage **)*((_QWORD *)this + 27);
      if ( v15 != *((char **)this + 29) )
      {
        if ( v16 == (struct OdmlMapDataPackage **)v15 )
        {
          *(_QWORD *)v15 = v3;
          *((_QWORD *)this + 28) += 8LL;
        }
        else
        {
          *(_QWORD *)v15 = *((_QWORD *)v15 - 1);
          *((_QWORD *)this + 28) += 8LL;
          memmove_0(v16 + 1, v16, v15 - (char *)v16 - 8);
          *v16 = v3;
        }
        return;
      }
      v12 = (struct OdmlMapDataPackage **)*((_QWORD *)this + 27);
      v14 = (_QWORD *)((char *)this + 216);
    }
    else
    {
      *((_DWORD *)a2 + 9) |= 8u;
      OdmlMapDataPackage::SetState(a2, 7);
      v14 = (_QWORD *)((char *)this + 216);
      v12 = (struct OdmlMapDataPackage **)*((_QWORD *)this + 28);
      if ( v12 != *((struct OdmlMapDataPackage ***)this + 29) )
      {
        *v12 = v3;
        *((_QWORD *)this + 28) += 8LL;
        return;
      }
    }
    v13 = &v17;
LABEL_35:
    std::vector<OdmlMapDataPackage *>::_Emplace_reallocate<OdmlMapDataPackage *>(v14, (__int64)v12, v13);
    return;
  }
  *((_DWORD *)a2 + 9) = 0;
  OdmlMapDataPackage::SetState(a2, 1);
  v6 = (__int64 *)*((_QWORD *)v3 + 11);
  v7 = 0;
  if ( !v6 )
    goto LABEL_17;
  do
  {
    for ( i = *v6; i != v6[1]; i += 8 )
    {
      if ( *(_DWORD *)(*(_QWORD *)i + 32LL) != 1 )
        goto LABEL_15;
    }
    *((_DWORD *)v6 + 9) = 0;
    v7 = (struct OdmlMapDataPackage *)v6;
    OdmlMapDataPackage::SetState(v6, 1);
    v8 = v6[1];
    for ( j = *v6; j != v8; j += 8 )
    {
      v10 = *((_QWORD *)this + 24);
      i = *(unsigned int *)(*(_QWORD *)j + 24LL);
      while ( v10 != *((_QWORD *)this + 25) )
      {
        if ( *(_DWORD *)(*(_QWORD *)v10 + 24LL) == (_DWORD)i )
        {
          std::vector<OdmlMapDataPackage *>::erase((char *)this + 192, &v18);
          break;
        }
        v10 += 8;
      }
    }
    v6 = (__int64 *)v6[11];
  }
  while ( v6 );
LABEL_15:
  if ( v7 )
  {
    v18 = v7;
    v3 = v7;
  }
  else
  {
LABEL_17:
    v7 = v3;
    v18 = v3;
  }
  if ( !(unsigned __int8)PackageManager::Contains(i, (char *)this + 192, *((unsigned int *)v3 + 6)) )
  {
    v12 = *(struct OdmlMapDataPackage ***)(v11 + 8);
    if ( v12 != *(struct OdmlMapDataPackage ***)(v11 + 16) )
    {
      *v12 = v7;
      *(_QWORD *)(v11 + 8) += 8LL;
      return;
    }
    v13 = &v18;
    v14 = (_QWORD *)v11;
    goto LABEL_35;
  }
}

```

## disassembly

```asm
0x18000ff9c  mov     [rsp+arg_0], rbx
0x18000ffa1  mov     [rsp+arg_10], rbp
0x18000ffa6  mov     [rsp+arg_8], rdx
0x18000ffab  push    rsi
0x18000ffac  push    rdi
0x18000ffad  push    r12
0x18000ffaf  push    r14
0x18000ffb1  push    r15
0x18000ffb3  sub     rsp, 20h
0x18000ffb7  mov     rbx, rdx
0x18000ffba  mov     rbp, rcx
0x18000ffbd  test    r8d, r8d
0x18000ffc0  js      loc_1800100C1
0x18000ffc6  xor     r8d, r8d
0x18000ffc9  mov     dword ptr [rdx+24h], 0
0x18000ffd0  mov     rcx, rbx
0x18000ffd3  lea     edx, [r8+1]
0x18000ffd7  call    ?SetState@OdmlMapDataPackage@@QEAAXW4__MIDL_odmlapi_0002@@J@Z; OdmlMapDataPackage::SetState(__MIDL_odmlapi_0002,long)
0x18000ffdc  mov     rdi, [rbx+58h]
0x18000ffe0  xor     esi, esi
0x18000ffe2  test    rdi, rdi
0x18000ffe5  jz      loc_18001007A
0x18000ffeb  mov     rcx, [rdi]
0x18000ffee  cmp     rcx, [rdi+8]
0x18000fff2  jz      short loc_180010003
0x18000fff4  mov     rax, [rcx]
0x18000fff7  cmp     dword ptr [rax+20h], 1
0x18000fffb  jnz     short loc_18001006B
0x18000fffd  add     rcx, 8
0x180010001  jmp     short loc_18000FFEE
0x180010003  xor     r8d, r8d
0x180010006  mov     dword ptr [rdi+24h], 0
0x18001000d  mov     rcx, rdi
0x180010010  mov     rsi, rdi
0x180010013  lea     edx, [r8+1]
0x180010017  call    ?SetState@OdmlMapDataPackage@@QEAAXW4__MIDL_odmlapi_0002@@J@Z; OdmlMapDataPackage::SetState(__MIDL_odmlapi_0002,long)
0x18001001c  mov     r12, [rdi+8]
0x180010020  mov     r14, [rdi]
0x180010023  cmp     r14, r12
0x180010026  jz      short loc_180010062
0x180010028  lea     r15, [rbp+0C0h]
0x18001002f  mov     rax, [r14]
0x180010032  mov     r8, [r15]
0x180010035  mov     ecx, [rax+18h]
0x180010038  cmp     r8, [r15+8]
0x18001003c  jz      short loc_180010059
0x18001003e  mov     rax, [r8]
0x180010041  cmp     [rax+18h], ecx
0x180010044  jz      short loc_18001004C
0x180010046  add     r8, 8
0x18001004a  jmp     short loc_180010038
0x18001004c  lea     rdx, [rsp+48h+arg_18]
0x180010051  mov     rcx, r15
0x180010054  call    ?erase@?$vector@PEAVOdmlMapDataPackage@@V?$allocator@PEAVOdmlMapDataPackage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVOdmlMapDataPackage@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@PEAVOdmlMapDataPackage@@@std@@@std@@@2@@Z; std::vector<OdmlMapDataPackage *>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<OdmlMapDataPackage *>>>)
0x180010059  add     r14, 8
0x18001005d  cmp     r14, r12
0x180010060  jnz     short loc_18001002F
0x180010062  mov     rdi, [rdi+58h]
0x180010066  test    rdi, rdi
0x180010069  jnz     short loc_18000FFEB
0x18001006b  test    rsi, rsi
0x18001006e  jz      short loc_18001007A
0x180010070  mov     [rsp+48h+arg_18], rsi
0x180010075  mov     rbx, rsi
0x180010078  jmp     short loc_180010082
0x18001007a  mov     rsi, rbx
0x18001007d  mov     [rsp+48h+arg_18], rbx
0x180010082  mov     r8d, [rbx+18h]
0x180010086  lea     r10, [rbp+0C0h]
0x18001008d  mov     rdx, r10
0x180010090  call    ?Contains@PackageManager@@AEAA_NAEBV?$vector@PEAVOdmlMapDataPackage@@V?$allocator@PEAVOdmlMapDataPackage@@@std@@@std@@I@Z; PackageManager::Contains(std::vector<OdmlMapDataPackage *> const &,uint)
0x180010095  test    al, al
0x180010097  jnz     loc_18001019D
0x18001009d  mov     rdx, [r10+8]
0x1800100a1  cmp     rdx, [r10+10h]
0x1800100a5  jz      short loc_1800100B4
0x1800100a7  mov     [rdx], rsi
0x1800100aa  add     qword ptr [r10+8], 8
0x1800100af  jmp     loc_18001019D
0x1800100b4  lea     r8, [rsp+48h+arg_18]
0x1800100b9  mov     rcx, r10
0x1800100bc  jmp     loc_180010198
0x1800100c1  cmp     r8d, 84010007h
0x1800100c8  jz      short loc_18001010F
0x1800100ca  cmp     r8d, 800704C7h
0x1800100d1  jz      short loc_18001010F
0x1800100d3  cmp     r8d, 800704D3h
0x1800100da  jz      short loc_18001010F
0x1800100dc  or      dword ptr [rdx+24h], 8
0x1800100e0  mov     rcx, rbx
0x1800100e3  mov     edx, 7
0x1800100e8  call    ?SetState@OdmlMapDataPackage@@QEAAXW4__MIDL_odmlapi_0002@@J@Z; OdmlMapDataPackage::SetState(__MIDL_odmlapi_0002,long)
0x1800100ed  lea     rcx, [rbp+0D8h]
0x1800100f4  mov     rdx, [rcx+8]
0x1800100f8  cmp     rdx, [rcx+10h]
0x1800100fc  jz      loc_180010193
0x180010102  mov     [rdx], rbx
0x180010105  add     qword ptr [rcx+8], 8
0x18001010a  jmp     loc_18001019D
0x18001010f  mov     eax, [rdx+20h]
0x180010112  xor     r8d, r8d
0x180010115  sub     eax, 4
0x180010118  mov     edx, 2
0x18001011d  mov     rcx, rbx
0x180010120  cmp     eax, edx
0x180010122  jbe     short loc_180010131
0x180010124  xor     edx, edx
0x180010126  mov     [rbx+24h], r8d
0x18001012a  call    ?SetState@OdmlMapDataPackage@@QEAAXW4__MIDL_odmlapi_0002@@J@Z; OdmlMapDataPackage::SetState(__MIDL_odmlapi_0002,long)
0x18001012f  jmp     short loc_18001019D
0x180010131  mov     dword ptr [rbx+24h], 1
0x180010138  mov     dword ptr [rbx+28h], 3
0x18001013f  call    ?SetState@OdmlMapDataPackage@@QEAAXW4__MIDL_odmlapi_0002@@J@Z; OdmlMapDataPackage::SetState(__MIDL_odmlapi_0002,long)
0x180010144  lea     r9, [rbp+0D8h]
0x18001014b  mov     rcx, [r9+8]
0x18001014f  mov     rdi, [r9]
0x180010152  cmp     rcx, [r9+10h]
0x180010156  jz      short loc_18001018D
0x180010158  cmp     rdi, rcx
0x18001015b  jnz     short loc_180010167
0x18001015d  mov     [rcx], rbx
0x180010160  add     qword ptr [r9+8], 8
0x180010165  jmp     short loc_18001019D
0x180010167  mov     rax, [rcx-8]
0x18001016b  mov     r8, rcx
0x18001016e  mov     [rcx], rax
0x180010171  sub     r8, rdi
0x180010174  add     qword ptr [r9+8], 8
0x180010179  add     r8, 0FFFFFFFFFFFFFFF8h; Size
0x18001017d  sub     rcx, r8; void *
0x180010180  mov     rdx, rdi; Src
0x180010183  call    memmove_0
0x180010188  mov     [rdi], rbx
0x18001018b  jmp     short loc_18001019D
0x18001018d  mov     rdx, rdi
0x180010190  mov     rcx, r9
0x180010193  lea     r8, [rsp+48h+arg_8]
0x180010198  call    ??$_Emplace_reallocate@PEAVOdmlMapDataPackage@@@?$vector@PEAVOdmlMapDataPackage@@V?$allocator@PEAVOdmlMapDataPackage@@@std@@@std@@AEAAPEAPEAVOdmlMapDataPackage@@QEAPEAV2@$$QEAPEAV2@@Z; std::vector<OdmlMapDataPackage *>::_Emplace_reallocate<OdmlMapDataPackage *>(OdmlMapDataPackage * * const,OdmlMapDataPackage * &&)
0x18001019d  mov     rbx, [rsp+48h+arg_0]
0x1800101a2  mov     rbp, [rsp+48h+arg_10]
0x1800101a7  add     rsp, 20h
0x1800101ab  pop     r15
0x1800101ad  pop     r14
0x1800101af  pop     r12
0x1800101b1  pop     rdi
0x1800101b2  pop     rsi
0x1800101b3  retn
```
