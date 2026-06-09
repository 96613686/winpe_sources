# DavCreateUncPath

- ea: `0x180003300`
- end: `0x180003543`
- name: `DavCreateUncPath`
- size: `579`
- prototype: `__int64 __fastcall(int *, _WORD *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180001e80`
- `0x1800027c0`

## callees

- `0x180003300`
- `0x180003550`
- `0x180005d88`
- `0x1800060cd`
- `0x180006100`

## pseudocode

```c
__int64 __fastcall DavCreateUncPath(int *a1, _WORD *a2, unsigned __int64 *a3)
{
  __int128 v6; // xmm0
  int v7; // eax
  __int64 v8; // rbx
  unsigned __int64 v9; // r15
  __int128 *v10; // r14
  _WORD *v11; // r13
  unsigned __int64 v12; // rbp
  unsigned __int64 v13; // rsi
  unsigned __int64 v14; // r12
  __int64 result; // rax
  unsigned __int64 v16; // rcx
  __int128 v18; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v19; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v20[2]; // [rsp+70h] [rbp-98h] BYREF
  __int16 *v21; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int16 *v22; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v23[2]; // [rsp+90h] [rbp-78h] BYREF
  _QWORD v24[2]; // [rsp+A0h] [rbp-68h] BYREF
  __int16 v25; // [rsp+B0h] [rbp-58h] BYREF
  wchar_t Buffer[7]; // [rsp+B2h] [rbp-56h] BYREF

  v18 = 0;
  DAV_STRING_VIEW::DAV_STRING_VIEW((DAV_STRING_VIEW *)&v19);
  DAV_STRING_VIEW::DAV_STRING_VIEW((DAV_STRING_VIEW *)v20);
  DAV_STRING_VIEW::DAV_STRING_VIEW((DAV_STRING_VIEW *)&v21);
  DAV_STRING_VIEW::DAV_STRING_VIEW((DAV_STRING_VIEW *)v23);
  DAV_STRING_VIEW::DAV_STRING_VIEW((DAV_STRING_VIEW *)v24);
  v6 = *(_OWORD *)(a1 + 2);
  *(_QWORD *)&v18 = L"\\\\";
  *((_QWORD *)&v18 + 1) = L"";
  v7 = *a1;
  v19 = v6;
  if ( (v7 & 1) != 0 )
  {
    v20[0] = L"@SSL";
    v20[1] = L"";
  }
  v8 = 6;
  if ( (v7 & 2) != 0 )
  {
    v21 = &v25;
    v25 = 64;
    StringCchPrintfExW(Buffer, 6u, &v22, 0, 0, L"%d", *((unsigned __int16 *)a1 + 2));
  }
  v9 = *a3;
  v23[0] = L"\\DavWWWRoot";
  v10 = &v18;
  v11 = 0;
  v23[1] = L"";
  v12 = 0;
  v24[0] = *((_QWORD *)a1 + 3);
  if ( v9 )
    v11 = a2;
  v24[1] = *((_QWORD *)a1 + 4);
  do
  {
    v13 = (__int64)(*((_QWORD *)v10 + 1) - *(_QWORD *)v10) >> 1;
    v14 = v13;
    if ( v9 < v13 )
      v14 = v9;
    memcpy_0(v11, *(const void **)v10, 2 * v14);
    v11 += v14;
    v9 -= v14;
    if ( v14 < v13 )
      goto LABEL_16;
    v12 += v14;
    ++v10;
    --v8;
  }
  while ( v8 );
  if ( v9 )
  {
    *v11 = 0;
    *a3 = v12 + 1;
    return 0;
  }
  else
  {
    while ( v8 )
    {
LABEL_16:
      v16 = v12 + ((__int64)(*((_QWORD *)v10 + 1) - *(_QWORD *)v10) >> 1);
      if ( v16 < v12 )
        return 534;
      ++v10;
      v12 = v16;
      --v8;
    }
    if ( v12 + 1 < v12 )
      return 534;
    if ( v11 )
      *(v11 - 1) = 0;
    result = 122;
    *a3 = v12 + 1;
  }
  return result;
}

```

## disassembly

```asm
0x180003300  mov     [rsp+arg_18], rbx
0x180003305  push    rbp
0x180003306  push    rsi
0x180003307  push    rdi
0x180003308  push    r12
0x18000330a  push    r13
0x18000330c  push    r14
0x18000330e  push    r15
0x180003310  sub     rsp, 0D0h
0x180003317  mov     rax, cs:__security_cookie
0x18000331e  xor     rax, rsp
0x180003321  mov     [rsp+108h+var_48], rax
0x180003329  mov     rdi, rcx
0x18000332c  mov     [rsp+108h+var_C8], r8
0x180003331  xorps   xmm0, xmm0
0x180003334  lea     rcx, [rsp+108h+var_A8]; this
0x180003339  movdqa  [rsp+108h+var_B8], xmm0
0x18000333f  mov     r15, r8
0x180003342  mov     rsi, rdx
0x180003345  call    ??0DAV_STRING_VIEW@@QEAA@XZ; DAV_STRING_VIEW::DAV_STRING_VIEW(void)
0x18000334a  lea     rcx, [rsp+108h+var_98]; this
0x18000334f  call    ??0DAV_STRING_VIEW@@QEAA@XZ; DAV_STRING_VIEW::DAV_STRING_VIEW(void)
0x180003354  lea     rcx, [rsp+108h+var_88]; this
0x18000335c  call    ??0DAV_STRING_VIEW@@QEAA@XZ; DAV_STRING_VIEW::DAV_STRING_VIEW(void)
0x180003361  lea     rcx, [rsp+108h+var_78]; this
0x180003369  call    ??0DAV_STRING_VIEW@@QEAA@XZ; DAV_STRING_VIEW::DAV_STRING_VIEW(void)
0x18000336e  lea     rcx, [rsp+108h+var_68]; this
0x180003376  call    ??0DAV_STRING_VIEW@@QEAA@XZ; DAV_STRING_VIEW::DAV_STRING_VIEW(void)
0x18000337b  movups  xmm0, xmmword ptr [rdi+8]
0x18000337f  lea     rax, asc_1800073C4; "\\\\"
0x180003386  mov     qword ptr [rsp+108h+var_B8], rax
0x18000338b  lea     rax, asc_1800073C4+4; ""
0x180003392  mov     qword ptr [rsp+108h+var_B8+8], rax
0x180003397  mov     eax, [rdi]
0x180003399  movaps  [rsp+108h+var_A8], xmm0
0x18000339e  test    al, 1
0x1800033a0  jz      short loc_1800033BA
0x1800033a2  lea     rcx, aSsl; "@SSL"
0x1800033a9  mov     [rsp+108h+var_98], rcx
0x1800033ae  lea     rcx, aSsl+8; ""
0x1800033b5  mov     [rsp+108h+var_90], rcx
0x1800033ba  mov     ebx, 6
0x1800033bf  test    al, 2
0x1800033c1  jnz     loc_1800034E0
0x1800033c7  mov     r15, [r15]
0x1800033ca  lea     rax, aDavwwwroot_0; "\\DavWWWRoot"
0x1800033d1  mov     [rsp+108h+var_78], rax
0x1800033d9  lea     r14, [rsp+108h+var_B8]
0x1800033de  lea     rax, aDavwwwroot_0+16h; ""
0x1800033e5  xor     r13d, r13d
0x1800033e8  mov     [rsp+108h+var_70], rax
0x1800033f0  xor     ebp, ebp
0x1800033f2  mov     rax, [rdi+18h]
0x1800033f6  test    r15, r15
0x1800033f9  mov     [rsp+108h+var_68], rax
0x180003401  mov     rax, [rdi+20h]
0x180003405  cmovnz  r13, rsi
0x180003409  mov     [rsp+108h+var_60], rax
0x180003411  mov     rdx, [r14]; Src
0x180003414  mov     rcx, r13; void *
0x180003417  mov     rsi, [r14+8]
0x18000341b  sub     rsi, rdx
0x18000341e  sar     rsi, 1
0x180003421  cmp     r15, rsi
0x180003424  mov     r12, rsi
0x180003427  cmovb   r12, r15
0x18000342b  lea     rdi, [r12+r12]
0x18000342f  mov     r8, rdi; Size
0x180003432  call    memcpy_0
0x180003437  add     r13, rdi
0x18000343a  sub     r15, r12
0x18000343d  cmp     r12, rsi
0x180003440  jnb     short loc_180003449
0x180003442  test    rbx, rbx
0x180003445  jz      short loc_180003456
0x180003447  jmp     short loc_180003481
0x180003449  add     rbp, r12
0x18000344c  add     r14, 10h
0x180003450  sub     rbx, 1
0x180003454  jnz     short loc_180003411
0x180003456  test    r15, r15
0x180003459  jz      short loc_18000347C
0x18000345b  mov     rdx, [rsp+108h+var_C8]
0x180003460  xor     eax, eax
0x180003462  mov     [r13+0], ax
0x180003467  lea     rax, [rbp+1]
0x18000346b  mov     [rdx], rax
0x18000346e  xor     eax, eax
0x180003470  jmp     short loc_180003498
0x180003472  add     r14, 10h
0x180003476  mov     rbp, rcx
0x180003479  dec     rbx
0x18000347c  test    rbx, rbx
0x18000347f  jz      short loc_1800034C3
0x180003481  mov     rcx, [r14+8]
0x180003485  sub     rcx, [r14]
0x180003488  sar     rcx, 1
0x18000348b  add     rcx, rbp
0x18000348e  cmp     rcx, rbp
0x180003491  jnb     short loc_180003472
0x180003493  mov     eax, 216h
0x180003498  mov     rcx, [rsp+108h+var_48]
0x1800034a0  xor     rcx, rsp; StackCookie
0x1800034a3  call    __security_check_cookie
0x1800034a8  mov     rbx, [rsp+108h+arg_18]
0x1800034b0  add     rsp, 0D0h
0x1800034b7  pop     r15
0x1800034b9  pop     r14
0x1800034bb  pop     r13
0x1800034bd  pop     r12
0x1800034bf  pop     rdi
0x1800034c0  pop     rsi
0x1800034c1  pop     rbp
0x1800034c2  retn
0x1800034c3  lea     rcx, [rbp+1]
0x1800034c7  cmp     rcx, rbp
0x1800034ca  jb      short loc_180003493
0x1800034cc  test    r13, r13
0x1800034cf  jnz     short loc_18000353A
0x1800034d1  mov     rdx, [rsp+108h+var_C8]
0x1800034d6  mov     eax, 7Ah ; 'z'
0x1800034db  mov     [rdx], rcx
0x1800034de  jmp     short loc_180003498
0x1800034e0  lea     rax, [rsp+108h+var_58]
0x1800034e8  xor     r9d, r9d; unsigned __int64 *
0x1800034eb  mov     [rsp+108h+var_88], rax
0x1800034f3  lea     r8, [rsp+108h+var_80]; unsigned __int16 **
0x1800034fb  mov     eax, 40h ; '@'
0x180003500  lea     rcx, [rsp+108h+Buffer]; Buffer
0x180003508  mov     [rsp+108h+var_58], ax
0x180003510  mov     rdx, rbx; unsigned __int64
0x180003513  movzx   eax, word ptr [rdi+4]
0x180003517  mov     [rsp+108h+var_D8], eax
0x18000351b  lea     rax, aD; "%d"
0x180003522  mov     [rsp+108h+var_E0], rax; unsigned __int16 *
0x180003527  mov     qword ptr [rsp+108h+var_E8], 0; unsigned int
0x180003530  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180003535  jmp     loc_1800033C7
0x18000353a  xor     eax, eax
0x18000353c  mov     [r13-2], ax
0x180003541  jmp     short loc_1800034D1
```
