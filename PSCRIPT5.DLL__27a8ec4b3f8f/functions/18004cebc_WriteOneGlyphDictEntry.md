# WriteOneGlyphDictEntry

- ea: `0x18004cebc`
- end: `0x18004d122`
- name: `WriteOneGlyphDictEntry`
- size: `614`
- prototype: `int __fastcall(__int64, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18004f4e4`

## callees

- `0x180001f20`
- `0x1800481e4`
- `0x180049bc4`
- `0x18004aae0`
- `0x18004b690`
- `0x18004b714`
- `0x18004cebc`
- `0x18004fa68`
- `0x18005f010`

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
  void (__fastcall *v11)(__int64, _QWORD, unsigned __int8 **, _WORD *, unsigned __int8 *, _QWORD); // rax
  unsigned __int16 v12; // dx
  void (*v13)(_BYTE *, __int64, const char *, ...); // rax
  unsigned __int16 v14; // ax
  unsigned __int8 FDIndex; // al
  const char *v16; // r8
  unsigned __int16 v17; // ax
  __int64 v18; // rcx
  int result; // eax
  __int64 v20; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v21[4]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v22[2]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int8 *v23; // [rsp+48h] [rbp-B8h] BYREF
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
  v11 = *(void (__fastcall **)(__int64, _QWORD, unsigned __int8 **, _WORD *, unsigned __int8 *, _QWORD))(a1 + 424);
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
  XCF_PutData(a1, (__int64)v24, v14);
  if ( *(_WORD *)(a1 + 14952) > 1u )
  {
    if ( *(_QWORD *)(a1 + 424) )
    {
      FDIndex = v21[0];
    }
    else
    {
      FDIndex = XCF_GetFDIndex(a1, v3);
      v21[0] = FDIndex;
    }
    v16 = "%02X";
    if ( !*(_DWORD *)(a1 + 7980) )
      v16 = "%c";
    (*(void (__fastcall **)(_BYTE *, __int64, const char *, _QWORD))(a1 + 360))(v24, 1024, v16, FDIndex);
    v17 = (*(__int64 (__fastcall **)(_BYTE *))(a1 + 336))(v24);
    XCF_PutData(a1, (__int64)v24, v17);
  }
  PutType1CharString(a1, v23, v22[0]);
  if ( *(_DWORD *)(a1 + 7980) )
    PutString(a1, (__int64)">");
  PutString(a1, (__int64)" |\r\n");
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
0x18004cebc  mov     [rsp-8+arg_18], rbx
0x18004cec1  push    rbp
0x18004cec2  push    rsi
0x18004cec3  push    rdi
0x18004cec4  push    r14
0x18004cec6  push    r15
0x18004cec8  lea     rbp, [rsp-360h]
0x18004ced0  sub     rsp, 460h
0x18004ced7  mov     rax, cs:__security_cookie
0x18004cede  xor     rax, rsp
0x18004cee1  mov     [rbp+380h+var_30], rax
0x18004cee8  xor     eax, eax
0x18004ceea  movsxd  rdi, edx
0x18004ceed  xor     r15d, r15d
0x18004cef0  mov     [rsp+480h+var_43C], ax
0x18004cef5  cmp     word ptr [rcx+3A68h], 1
0x18004cefd  mov     rsi, r8
0x18004cf00  mov     [rsp+480h+var_438], rax
0x18004cf05  mov     rbx, rcx
0x18004cf08  movzx   eax, word ptr [rcx+1F28h]
0x18004cf0f  setnbe  r15b
0x18004cf13  mov     [rsp+480h+var_440], 0
0x18004cf18  cmp     ax, 0FFFFh
0x18004cf1c  jnz     short loc_18004CF23
0x18004cf1e  xor     r14d, r14d
0x18004cf21  jmp     short loc_18004CF27
0x18004cf23  movzx   r14d, ax
0x18004cf27  mov     rax, [rcx+1A8h]
0x18004cf2e  test    rax, rax
0x18004cf31  jnz     short loc_18004CF73
0x18004cf33  cmp     byte ptr [rcx+1F34h], 2
0x18004cf3a  jz      short loc_18004CF45
0x18004cf3c  mov     edx, edi
0x18004cf3e  call    ProcessOneCharString
0x18004cf43  jmp     short loc_18004CF4B
0x18004cf45  mov     [rcx+3768h], edi
0x18004cf4b  lea     r8, [rsp+480h+var_43C]
0x18004cf50  mov     rcx, rbx
0x18004cf53  lea     rdx, [rsp+480h+var_438]
0x18004cf58  call    GetCIDCharString
0x18004cf5d  test    edi, edi
0x18004cf5f  jz      short loc_18004CF6F
0x18004cf61  mov     rax, [rbx+3A58h]
0x18004cf68  movzx   edx, word ptr [rax+rdi*2-2]
0x18004cf6d  jmp     short loc_18004CFA0
0x18004cf6f  xor     edx, edx
0x18004cf71  jmp     short loc_18004CFA0
0x18004cf73  mov     rcx, [rcx+1B0h]
0x18004cf7a  lea     r9, [rsp+480h+var_43C]
0x18004cf7f  mov     [rsp+480h+var_458], rcx
0x18004cf84  lea     r8, [rsp+480h+var_438]
0x18004cf89  lea     rcx, [rsp+480h+var_440]
0x18004cf8e  mov     edx, edi
0x18004cf90  mov     [rsp+480h+var_460], rcx
0x18004cf95  mov     rcx, rbx
0x18004cf98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf9d  movzx   edx, di
0x18004cfa0  cmp     dword ptr [rbx+1F2Ch], 0
0x18004cfa7  mov     rax, [rbx+168h]
0x18004cfae  movzx   r9d, dx
0x18004cfb2  jz      short loc_18004CFD0
0x18004cfb4  mov     r14d, 400h
0x18004cfba  lea     r8, aD_2; "%d <"
0x18004cfc1  mov     edx, r14d
0x18004cfc4  lea     rcx, [rsp+480h+var_430]
0x18004cfc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfce  jmp     short loc_18004CFFC
0x18004cfd0  movzx   edx, [rsp+480h+var_43C]
0x18004cfd5  lea     r8, aDD; "%d %d : "
0x18004cfdc  movzx   ecx, r14w
0x18004cfe0  mov     r14d, 400h
0x18004cfe6  add     ecx, r15d
0x18004cfe9  add     edx, ecx
0x18004cfeb  lea     rcx, [rsp+480h+var_430]
0x18004cff0  mov     dword ptr [rsp+480h+var_460], edx
0x18004cff4  mov     edx, r14d
0x18004cff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cffc  mov     rax, [rbx+150h]
0x18004d003  lea     rcx, [rsp+480h+var_430]
0x18004d008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d00d  movzx   r8d, ax
0x18004d011  lea     rdx, [rsp+480h+var_430]
0x18004d016  mov     rcx, rbx
0x18004d019  call    XCF_PutData
0x18004d01e  cmp     word ptr [rbx+3A68h], 1
0x18004d026  jbe     short loc_18004D09A
0x18004d028  cmp     qword ptr [rbx+1A8h], 0
0x18004d030  jnz     short loc_18004D042
0x18004d032  mov     edx, edi
0x18004d034  mov     rcx, rbx
0x18004d037  call    XCF_GetFDIndex
0x18004d03c  mov     [rsp+480h+var_440], al
0x18004d040  jmp     short loc_18004D046
0x18004d042  mov     al, [rsp+480h+var_440]
0x18004d046  cmp     dword ptr [rbx+1F2Ch], 0
0x18004d04d  lea     rcx, [rsp+480h+var_430]
0x18004d052  mov     r10, [rbx+168h]
0x18004d059  lea     r8, a02x; "%02X"
0x18004d060  movzx   r9d, al
0x18004d064  mov     rdx, r14
0x18004d067  mov     rax, r10
0x18004d06a  jnz     short loc_18004D073
0x18004d06c  lea     r8, aC_0; "%c"
0x18004d073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d078  mov     rax, [rbx+150h]
0x18004d07f  lea     rcx, [rsp+480h+var_430]
0x18004d084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d089  movzx   r8d, ax
0x18004d08d  lea     rdx, [rsp+480h+var_430]
0x18004d092  mov     rcx, rbx
0x18004d095  call    XCF_PutData
0x18004d09a  movzx   r8d, [rsp+480h+var_43C]
0x18004d0a0  mov     rcx, rbx
0x18004d0a3  mov     rdx, [rsp+480h+var_438]
0x18004d0a8  call    PutType1CharString
0x18004d0ad  cmp     dword ptr [rbx+1F2Ch], 0
0x18004d0b4  jz      short loc_18004D0C5
0x18004d0b6  lea     rdx, asc_180064940; ">"
0x18004d0bd  mov     rcx, rbx
0x18004d0c0  call    PutString
0x18004d0c5  lea     rdx, asc_18006CA4C; " |\r\n"
0x18004d0cc  mov     rcx, rbx
0x18004d0cf  call    PutString
0x18004d0d4  mov     rcx, [rbx+65F0h]
0x18004d0db  mov     rdx, rdi
0x18004d0de  sar     rdx, 3
0x18004d0e2  and     edi, 7
0x18004d0e5  movzx   eax, byte ptr [rdx+rcx]
0x18004d0e9  bts     eax, edi
0x18004d0ec  mov     [rdx+rcx], al
0x18004d0ef  test    rsi, rsi
0x18004d0f2  jz      short loc_18004D0FB
0x18004d0f4  movzx   eax, [rsp+480h+var_43C]
0x18004d0f9  add     [rsi], eax
0x18004d0fb  mov     rcx, [rbp+380h+var_30]
0x18004d102  xor     rcx, rsp; StackCookie
0x18004d105  call    __security_check_cookie
0x18004d10a  mov     rbx, [rsp+480h+arg_18]
0x18004d112  add     rsp, 460h
0x18004d119  pop     r15
0x18004d11b  pop     r14
0x18004d11d  pop     rdi
0x18004d11e  pop     rsi
0x18004d11f  pop     rbp
0x18004d120  retn
```
