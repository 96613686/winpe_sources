# BinXmlReader::IsNextSubstValueNull(void)

- ea: `0x180003860`
- end: `0x180003a56`
- name: `?IsNextSubstValueNull@BinXmlReader@@AEAA_NXZ`
- size: `502`
- prototype: `bool __fastcall(BinXmlReader *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004070`

## callees

- `0x180003860`
- `0x1800231d0`
- `0x180023548`
- `0x180038fb4`

## pseudocode

```c
char __fastcall BinXmlReader::IsNextSubstValueNull(BinXmlReader *this)
{
  __int64 v2; // r11
  __int64 v3; // rax
  char v4; // r9
  __int64 v5; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r11
  __int64 v10; // rcx
  unsigned int v11; // r9d
  unsigned int v12; // r8d
  __int64 v13; // rbx
  __int64 v14; // r11
  __int64 v15; // rcx
  int v16; // edx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int128 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v20; // [rsp+30h] [rbp-28h]
  int v21; // [rsp+38h] [rbp-20h]
  int v22; // [rsp+3Ch] [rbp-1Ch]
  int v23; // [rsp+40h] [rbp-18h]

  if ( *((_BYTE *)this + 188) )
    return 0;
  v2 = *((_QWORD *)this + 2);
  v3 = *(unsigned int *)(v2 + 8);
  if ( (unsigned int)v3 >= *(_DWORD *)(v2 + 12) )
LABEL_17:
    UserBuffer::ThrowUnexpectedEOFException();
  v4 = *(_BYTE *)(v3 + *(_QWORD *)v2);
  *(_DWORD *)(v2 + 8) = v3 + 1;
  if ( v4 != 14 )
    goto LABEL_4;
  v7 = *((_QWORD *)this + 2);
  v8 = *(unsigned int *)(v7 + 8);
  if ( (unsigned int)(*(_DWORD *)(v7 + 12) - v8) < 2 )
    goto LABEL_17;
  v9 = *(unsigned __int16 *)(v8 + *(_QWORD *)v7);
  *(_DWORD *)(v7 + 8) = v8 + 2;
  v10 = *((_QWORD *)this + 9);
  v11 = *(_DWORD *)(v10 - 16);
  if ( v11 )
  {
    v12 = *((_DWORD *)this + 3);
    if ( v11 > v12 )
      goto LABEL_17;
    v13 = *(_QWORD *)this;
  }
  else
  {
    v17 = 5LL * *(unsigned __int16 *)(v10 - 8);
    v18 = *((_QWORD *)this + 3);
    v12 = *(_DWORD *)(v18 + 8 * v17 + 32);
    v13 = *(_QWORD *)(v18 + 8 * v17 + 24);
    if ( v12 < 4 )
      goto LABEL_17;
    v11 = 4;
  }
  if ( v11 >= v12 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
    }
    v21 = 13;
    v22 = -1;
    v20 = 0;
    v23 = 1492;
    pExceptionObject = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v14 = 4 * v9;
  if ( v12 - v11 < (unsigned __int64)(v14 + 4) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids, 13);
    }
    v21 = 13;
    v22 = -1;
    v20 = 0;
    v23 = 1497;
    pExceptionObject = 0;
    throw (EvtException *)&pExceptionObject;
  }
  if ( *(_BYTE *)(v14 + v11 + v13 + 2) )
  {
LABEL_4:
    v5 = *((_QWORD *)this + 2);
    if ( (unsigned int)v3 <= *(_DWORD *)(v5 + 12) )
    {
      *(_DWORD *)(v5 + 8) = v3;
      return 0;
    }
    goto LABEL_17;
  }
  v15 = *((_QWORD *)this + 2);
  if ( !*(_QWORD *)v15 )
    goto LABEL_17;
  v16 = *(_DWORD *)(v15 + 8);
  if ( *(_DWORD *)(v15 + 12) == v16 )
    goto LABEL_17;
  *(_DWORD *)(v15 + 8) = v16 + 1;
  return 1;
}

```

## disassembly

```asm
0x180003860  push    rbx
0x180003862  sub     rsp, 50h
0x180003866  cmp     byte ptr [rcx+0BCh], 0
0x18000386d  mov     r10, rcx
0x180003870  jnz     short loc_1800038A9
0x180003872  mov     r11, [rcx+10h]
0x180003876  mov     eax, [r11+8]
0x18000387a  cmp     eax, [r11+0Ch]
0x18000387e  jnb     loc_180003944
0x180003884  mov     rdx, [r11]
0x180003887  lea     ecx, [rax+1]
0x18000388a  movzx   r9d, byte ptr [rax+rdx]
0x18000388f  mov     [r11+8], ecx
0x180003893  cmp     r9b, 0Eh
0x180003897  jz      short loc_1800038B1
0x180003899  mov     rcx, [r10+10h]
0x18000389d  cmp     eax, [rcx+0Ch]
0x1800038a0  ja      loc_180003944
0x1800038a6  mov     [rcx+8], eax
0x1800038a9  xor     al, al
0x1800038ab  add     rsp, 50h
0x1800038af  pop     rbx
0x1800038b0  retn
0x1800038b1  mov     r8, [r10+10h]
0x1800038b5  mov     r9d, [r8+8]
0x1800038b9  mov     ecx, [r8+0Ch]
0x1800038bd  sub     ecx, r9d
0x1800038c0  cmp     ecx, 2
0x1800038c3  jb      short loc_180003944
0x1800038c5  mov     rcx, [r8]
0x1800038c8  movzx   r11d, word ptr [r9+rcx]
0x1800038cd  lea     ecx, [r9+2]
0x1800038d1  mov     [r8+8], ecx
0x1800038d5  mov     rcx, [r10+48h]
0x1800038d9  mov     r9d, [rcx-10h]
0x1800038dd  test    r9d, r9d
0x1800038e0  jz      short loc_18000394A
0x1800038e2  mov     r8d, [r10+0Ch]
0x1800038e6  cmp     r9d, r8d
0x1800038e9  ja      short loc_180003944
0x1800038eb  mov     rbx, [r10]
0x1800038ee  cmp     r9d, r8d
0x1800038f1  jnb     short loc_18000396E
0x1800038f3  sub     r8d, r9d
0x1800038f6  lea     r11, ds:0[r11*4]
0x1800038fe  mov     edx, r8d
0x180003901  lea     rcx, [r11+4]
0x180003905  cmp     rdx, rcx
0x180003908  jb      loc_1800039E2
0x18000390e  mov     ecx, r9d
0x180003911  add     rcx, r11
0x180003914  cmp     byte ptr [rcx+rbx+2], 0
0x180003919  jnz     loc_180003899
0x18000391f  mov     rcx, [r10+10h]
0x180003923  cmp     qword ptr [rcx], 0
0x180003927  jz      short loc_180003944
0x180003929  mov     eax, [rcx+0Ch]
0x18000392c  mov     edx, [rcx+8]
0x18000392f  sub     eax, edx
0x180003931  cmp     eax, 1
0x180003934  jb      short loc_180003944
0x180003936  lea     eax, [rdx+1]
0x180003939  mov     [rcx+8], eax
0x18000393c  mov     al, 1
0x18000393e  add     rsp, 50h
0x180003942  pop     rbx
0x180003943  retn
0x180003944  call    ?ThrowUnexpectedEOFException@UserBuffer@@CAXXZ; UserBuffer::ThrowUnexpectedEOFException(void)
0x18000394a  movzx   ecx, word ptr [rcx-8]
0x18000394e  lea     rdx, [rcx+rcx*4]
0x180003952  mov     rcx, [r10+18h]
0x180003956  mov     r8d, [rcx+rdx*8+20h]
0x18000395b  mov     rbx, [rcx+rdx*8+18h]
0x180003960  cmp     r8d, 4
0x180003964  jb      short loc_180003944
0x180003966  mov     r9d, 4
0x18000396c  jmp     short loc_1800038EE
0x18000396e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003975  lea     rax, WPP_GLOBAL_Control
0x18000397c  cmp     rcx, rax
0x18000397f  jz      short loc_1800039A8
0x180003981  test    byte ptr [rcx+1Ch], 2
0x180003985  jz      short loc_1800039A8
0x180003987  cmp     byte ptr [rcx+19h], 2
0x18000398b  jb      short loc_1800039A8
0x18000398d  mov     rcx, [rcx+10h]
0x180003991  lea     r8, WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids
0x180003998  mov     edx, 26h ; '&'
0x18000399d  mov     r9d, 0Dh
0x1800039a3  call    WPP_SF_D
0x1800039a8  xorps   xmm0, xmm0
0x1800039ab  mov     [rsp+58h+var_20], 0Dh
0x1800039b3  xor     eax, eax
0x1800039b5  mov     [rsp+58h+var_1C], 0FFFFFFFFh
0x1800039bd  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800039c4  mov     [rsp+58h+var_28], rax
0x1800039c9  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800039ce  mov     [rsp+58h+var_18], 5D4h
0x1800039d6  movdqu  [rsp+58h+pExceptionObject], xmm0
0x1800039dc  call    _CxxThrowException_0
0x1800039e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039e9  lea     rax, WPP_GLOBAL_Control
0x1800039f0  cmp     rcx, rax
0x1800039f3  jz      short loc_180003A1C
0x1800039f5  test    byte ptr [rcx+1Ch], 2
0x1800039f9  jz      short loc_180003A1C
0x1800039fb  cmp     byte ptr [rcx+19h], 2
0x1800039ff  jb      short loc_180003A1C
0x180003a01  mov     rcx, [rcx+10h]
0x180003a05  lea     r8, WPP_2e7dc5ef0fe83399c91a1315b54063e2_Traceguids
0x180003a0c  mov     edx, 27h ; '''
0x180003a11  mov     r9d, 0Dh
0x180003a17  call    WPP_SF_D
0x180003a1c  xorps   xmm0, xmm0
0x180003a1f  mov     [rsp+58h+var_20], 0Dh
0x180003a27  xor     eax, eax
0x180003a29  mov     [rsp+58h+var_1C], 0FFFFFFFFh
0x180003a31  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180003a38  mov     [rsp+58h+var_28], rax
0x180003a3d  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180003a42  mov     [rsp+58h+var_18], 5D9h
0x180003a4a  movdqu  [rsp+58h+pExceptionObject], xmm0
0x180003a50  call    _CxxThrowException_0
```
