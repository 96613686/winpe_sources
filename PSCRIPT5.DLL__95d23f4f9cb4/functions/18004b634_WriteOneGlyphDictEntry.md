# WriteOneGlyphDictEntry

- ea: `0x18004b634`
- end: `0x18004b899`
- name: `WriteOneGlyphDictEntry`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18004dc54`

## callees

- `0x180001ee0`
- `0x1800468bc`
- `0x180048354`
- `0x18004926c`
- `0x180049e14`
- `0x180049e98`
- `0x18004b634`
- `0x18004e1c8`
- `0x18005d010`

## pseudocode

```c
int __fastcall WriteOneGlyphDictEntry(__int64 a1, unsigned int a2, _DWORD *a3)
{
  __int64 v3; // rdi
  bool v4; // cf
  bool v5; // zf
  unsigned __int16 v8; // ax
  BOOL v9; // r15d
  unsigned __int16 v10; // r14
  void (__fastcall *v11)(__int64, _QWORD, __int64 *, _WORD *, _BYTE *, _QWORD); // rax
  unsigned __int16 v12; // dx
  void (*v13)(_BYTE *, __int64, const char *, ...); // rax
  unsigned __int16 v14; // ax
  unsigned __int8 FDIndex; // al
  const char *v16; // r8
  unsigned __int16 v17; // ax
  __int64 v18; // rcx
  int result; // eax
  __int64 v20; // [rsp+20h] [rbp-E0h]
  _BYTE v21[4]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v22[2]; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v24[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = (int)a2;
  v22[0] = 0;
  v4 = *(_WORD *)(a1 + 14952) == 0;
  v5 = *(_WORD *)(a1 + 14952) == 1;
  v23 = 0;
  v8 = *(_WORD *)(a1 + 7976);
  v9 = !v4 && !v5;
  v21[0] = 0;
  if ( v8 == 0xFFFF )
    v10 = 0;
  else
    v10 = v8;
  v11 = *(void (__fastcall **)(__int64, _QWORD, __int64 *, _WORD *, _BYTE *, _QWORD))(a1 + 424);
  if ( v11 )
  {
    v11(a1, a2, &v23, v22, v21, *(_QWORD *)(a1 + 432));
    v12 = v3;
  }
  else
  {
    if ( *(_BYTE *)(a1 + 7988) == 2 )
      *(_DWORD *)(a1 + 14184) = a2;
    else
      ProcessOneCharString(a1, a2);
    GetCIDCharString(a1, &v23, v22);
    if ( (_DWORD)v3 )
      v12 = *(_WORD *)(*(_QWORD *)(a1 + 14936) + 2 * v3 - 2);
    else
      v12 = 0;
  }
  v13 = *(void (**)(_BYTE *, __int64, const char *, ...))(a1 + 360);
  if ( *(_DWORD *)(a1 + 7980) )
  {
    v13(v24, 1024, "%d <", v12);
  }
  else
  {
    LODWORD(v20) = v9 + v10 + v22[0];
    v13(v24, 1024, "%d %d : ", v12, v20);
  }
  v14 = (*(__int64 (__fastcall **)(_BYTE *))(a1 + 336))(v24);
  XCF_PutData(a1, v24, v14);
  if ( *(_WORD *)(a1 + 14952) > 1u )
  {
    if ( *(_QWORD *)(a1 + 424) )
    {
      FDIndex = v21[0];
    }
    else
    {
      FDIndex = XCF_GetFDIndex(a1, (unsigned int)v3);
      v21[0] = FDIndex;
    }
    v16 = "%02X";
    if ( !*(_DWORD *)(a1 + 7980) )
      v16 = "%c";
    (*(void (__fastcall **)(_BYTE *, __int64, const char *, _QWORD))(a1 + 360))(v24, 1024, v16, FDIndex);
    v17 = (*(__int64 (__fastcall **)(_BYTE *))(a1 + 336))(v24);
    XCF_PutData(a1, v24, v17);
  }
  PutType1CharString(a1, v23, v22[0]);
  if ( *(_DWORD *)(a1 + 7980) )
    PutString(a1, ">");
  PutString(a1, " |\r\n");
  v18 = *(_QWORD *)(a1 + 26096);
  result = *(unsigned __int8 *)((v3 >> 3) + v18) | (1 << (v3 & 7));
  *(_BYTE *)((v3 >> 3) + v18) = result;
  if ( a3 )
  {
    result = v22[0];
    *a3 += v22[0];
  }
  return result;
}

```

## disassembly

```asm
0x18004b634  mov     [rsp-8+arg_18], rbx
0x18004b639  push    rbp
0x18004b63a  push    rsi
0x18004b63b  push    rdi
0x18004b63c  push    r14
0x18004b63e  push    r15
0x18004b640  lea     rbp, [rsp-360h]
0x18004b648  sub     rsp, 460h
0x18004b64f  mov     rax, cs:__security_cookie
0x18004b656  xor     rax, rsp
0x18004b659  mov     [rbp+380h+var_30], rax
0x18004b660  xor     eax, eax
0x18004b662  movsxd  rdi, edx
0x18004b665  xor     r15d, r15d
0x18004b668  mov     [rsp+480h+var_43C], ax
0x18004b66d  cmp     word ptr [rcx+3A68h], 1
0x18004b675  mov     rsi, r8
0x18004b678  mov     [rsp+480h+var_438], rax
0x18004b67d  mov     rbx, rcx
0x18004b680  movzx   eax, word ptr [rcx+1F28h]
0x18004b687  setnbe  r15b
0x18004b68b  mov     [rsp+480h+var_440], 0
0x18004b690  cmp     ax, 0FFFFh
0x18004b694  jnz     short loc_18004B69B
0x18004b696  xor     r14d, r14d
0x18004b699  jmp     short loc_18004B69F
0x18004b69b  movzx   r14d, ax
0x18004b69f  mov     rax, [rcx+1A8h]
0x18004b6a6  test    rax, rax
0x18004b6a9  jnz     short loc_18004B6EB
0x18004b6ab  cmp     byte ptr [rcx+1F34h], 2
0x18004b6b2  jz      short loc_18004B6BD
0x18004b6b4  mov     edx, edi
0x18004b6b6  call    ProcessOneCharString
0x18004b6bb  jmp     short loc_18004B6C3
0x18004b6bd  mov     [rcx+3768h], edi
0x18004b6c3  lea     r8, [rsp+480h+var_43C]
0x18004b6c8  mov     rcx, rbx
0x18004b6cb  lea     rdx, [rsp+480h+var_438]
0x18004b6d0  call    GetCIDCharString
0x18004b6d5  test    edi, edi
0x18004b6d7  jz      short loc_18004B6E7
0x18004b6d9  mov     rax, [rbx+3A58h]
0x18004b6e0  movzx   edx, word ptr [rax+rdi*2-2]
0x18004b6e5  jmp     short loc_18004B718
0x18004b6e7  xor     edx, edx
0x18004b6e9  jmp     short loc_18004B718
0x18004b6eb  mov     rcx, [rcx+1B0h]
0x18004b6f2  lea     r9, [rsp+480h+var_43C]
0x18004b6f7  mov     [rsp+480h+var_458], rcx
0x18004b6fc  lea     r8, [rsp+480h+var_438]
0x18004b701  lea     rcx, [rsp+480h+var_440]
0x18004b706  mov     edx, edi
0x18004b708  mov     [rsp+480h+var_460], rcx
0x18004b70d  mov     rcx, rbx
0x18004b710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b715  movzx   edx, di
0x18004b718  cmp     dword ptr [rbx+1F2Ch], 0
0x18004b71f  mov     rax, [rbx+168h]
0x18004b726  movzx   r9d, dx
0x18004b72a  jz      short loc_18004B748
0x18004b72c  mov     r14d, 400h
0x18004b732  lea     r8, aD_2; "%d <"
0x18004b739  mov     edx, r14d
0x18004b73c  lea     rcx, [rsp+480h+var_430]
0x18004b741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b746  jmp     short loc_18004B774
0x18004b748  movzx   edx, [rsp+480h+var_43C]
0x18004b74d  lea     r8, aDD; "%d %d : "
0x18004b754  movzx   ecx, r14w
0x18004b758  mov     r14d, 400h
0x18004b75e  add     ecx, r15d
0x18004b761  add     edx, ecx
0x18004b763  lea     rcx, [rsp+480h+var_430]
0x18004b768  mov     dword ptr [rsp+480h+var_460], edx
0x18004b76c  mov     edx, r14d
0x18004b76f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b774  mov     rax, [rbx+150h]
0x18004b77b  lea     rcx, [rsp+480h+var_430]
0x18004b780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b785  movzx   r8d, ax
0x18004b789  lea     rdx, [rsp+480h+var_430]
0x18004b78e  mov     rcx, rbx
0x18004b791  call    XCF_PutData
0x18004b796  cmp     word ptr [rbx+3A68h], 1
0x18004b79e  jbe     short loc_18004B812
0x18004b7a0  cmp     qword ptr [rbx+1A8h], 0
0x18004b7a8  jnz     short loc_18004B7BA
0x18004b7aa  mov     edx, edi
0x18004b7ac  mov     rcx, rbx
0x18004b7af  call    XCF_GetFDIndex
0x18004b7b4  mov     [rsp+480h+var_440], al
0x18004b7b8  jmp     short loc_18004B7BE
0x18004b7ba  mov     al, [rsp+480h+var_440]
0x18004b7be  cmp     dword ptr [rbx+1F2Ch], 0
0x18004b7c5  lea     rcx, [rsp+480h+var_430]
0x18004b7ca  mov     r10, [rbx+168h]
0x18004b7d1  lea     r8, a02x; "%02X"
0x18004b7d8  movzx   r9d, al
0x18004b7dc  mov     rdx, r14
0x18004b7df  mov     rax, r10
0x18004b7e2  jnz     short loc_18004B7EB
0x18004b7e4  lea     r8, aC_0; "%c"
0x18004b7eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b7f0  mov     rax, [rbx+150h]
0x18004b7f7  lea     rcx, [rsp+480h+var_430]
0x18004b7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b801  movzx   r8d, ax
0x18004b805  lea     rdx, [rsp+480h+var_430]
0x18004b80a  mov     rcx, rbx
0x18004b80d  call    XCF_PutData
0x18004b812  movzx   r8d, [rsp+480h+var_43C]
0x18004b818  mov     rcx, rbx
0x18004b81b  mov     rdx, [rsp+480h+var_438]
0x18004b820  call    PutType1CharString
0x18004b825  cmp     dword ptr [rbx+1F2Ch], 0
0x18004b82c  jz      short loc_18004B83D
0x18004b82e  lea     rdx, asc_180062950; ">"
0x18004b835  mov     rcx, rbx
0x18004b838  call    PutString
0x18004b83d  lea     rdx, asc_18006AA8C; " |\r\n"
0x18004b844  mov     rcx, rbx
0x18004b847  call    PutString
0x18004b84c  mov     rcx, [rbx+65F0h]
0x18004b853  mov     rdx, rdi
0x18004b856  sar     rdx, 3
0x18004b85a  and     edi, 7
0x18004b85d  movzx   eax, byte ptr [rdx+rcx]
0x18004b861  bts     eax, edi
0x18004b864  mov     [rdx+rcx], al
0x18004b867  test    rsi, rsi
0x18004b86a  jz      short loc_18004B873
0x18004b86c  movzx   eax, [rsp+480h+var_43C]
0x18004b871  add     [rsi], eax
0x18004b873  mov     rcx, [rbp+380h+var_30]
0x18004b87a  xor     rcx, rsp; StackCookie
0x18004b87d  call    __security_check_cookie
0x18004b882  mov     rbx, [rsp+480h+arg_18]
0x18004b88a  add     rsp, 460h
0x18004b891  pop     r15
0x18004b893  pop     r14
0x18004b895  pop     rdi
0x18004b896  pop     rsi
0x18004b897  pop     rbp
0x18004b898  retn
```
