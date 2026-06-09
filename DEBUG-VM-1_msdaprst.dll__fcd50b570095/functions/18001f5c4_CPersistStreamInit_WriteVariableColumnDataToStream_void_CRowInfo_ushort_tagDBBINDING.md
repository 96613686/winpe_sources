# CPersistStreamInit::WriteVariableColumnDataToStream(void *,CRowInfo &,ushort,tagDBBINDING *)

- ea: `0x18001f5c4`
- end: `0x18001f7ae`
- name: `?WriteVariableColumnDataToStream@CPersistStreamInit@@AEAAJPEAXAEAVCRowInfo@@GPEAUtagDBBINDING@@@Z`
- size: `490`
- prototype: `__int64 __usercall@<rax>(CPersistStreamInit *__hidden this@<rcx>, void *@<rdx>, struct CRowInfo *@<r8>, unsigned __int16@<r9w>, struct tagDBBINDING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18001c994`

## callees

- `0x180001d94`
- `0x180001dd8`
- `0x1800041f8`
- `0x18001ac00`
- `0x18001c36c`
- `0x18001f5c4`
- `0x18002e060`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18001f6b7`
- `KERNEL32!MultiByteToWideChar` at `0x18001f6d7`
- `KERNEL32!MultiByteToWideChar` at `0x18001f724`
- `KERNEL32!MultiByteToWideChar` at `0x18001f6b7`
- `KERNEL32!MultiByteToWideChar` at `0x18001f6d7`
- `KERNEL32!MultiByteToWideChar` at `0x18001f724`
- `ole32!CoTaskMemFree` at `0x18001f76b`
- `ole32!CoTaskMemFree` at `0x18001f76b`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteVariableColumnDataToStream(
        CPersistStreamInit *this,
        unsigned __int16 *a2,
        struct CRowInfo *a3,
        unsigned __int16 a4,
        struct tagDBBINDING *a5)
{
  __int16 v8; // r10
  unsigned __int16 Type; // r14
  int v10; // r15d
  __int64 cbMaxLen_low; // rbx
  __int16 v13; // r10
  unsigned __int16 v14; // r14
  int v15; // eax
  WCHAR *lpWideCharStr; // rbp
  unsigned int v17; // eax
  unsigned __int16 *v18; // rdx
  unsigned __int128 v19; // rax
  unsigned int v20; // ebx
  int cchWideChar; // [rsp+30h] [rbp-858h]
  WCHAR WideCharStr[1024]; // [rsp+40h] [rbp-848h] BYREF

  Type = CMetaData::mdGetType(a3, a4);
  if ( (v8 & 0x4000) != 0 )
  {
    a2 = *(unsigned __int16 **)a2;
    v10 = 1;
  }
  else
  {
    v10 = 0;
  }
  cbMaxLen_low = *((_QWORD *)a3 + 11);
  if ( *(_DWORD *)(cbMaxLen_low + a5->obStatus) == 4 )
  {
    cbMaxLen_low = LODWORD(a5->cbMaxLen);
    if ( cbMaxLen_low != a5->cbMaxLen )
      return 2147500037LL;
  }
  else
  {
    LODWORD(cbMaxLen_low) = *(_DWORD *)(cbMaxLen_low + a5->obLength);
  }
  v13 = v8 & 0xBFFF;
  v14 = Type & 0xBFFF;
  if ( v13 == 130 )
  {
    v15 = CPersistStreamInit::TextOutW(this, a2, (unsigned int)cbMaxLen_low >> 1, v14);
LABEL_21:
    v20 = v15;
    goto LABEL_22;
  }
  if ( v13 != 129 )
  {
    v15 = CPersistStreamInit::BinaryOut(this, (unsigned __int8 *)a2, cbMaxLen_low);
    goto LABEL_21;
  }
  if ( (unsigned int)(2 * cbMaxLen_low) >= 0x400 )
  {
    cchWideChar = MultiByteToWideChar(0, 0, (LPCCH)a2, cbMaxLen_low, 0, 0);
    v19 = (unsigned int)(cchWideChar + 1) * (unsigned __int128)2uLL;
    if ( !is_mul_ok((unsigned int)(cchWideChar + 1), 2u) )
      LODWORD(v19) = -1;
    lpWideCharStr = (WCHAR *)MMMAlloc(v19, DWORD2(v19));
    if ( !lpWideCharStr )
      return 2147942414LL;
    v17 = MultiByteToWideChar(0, 0, (LPCCH)a2, cbMaxLen_low, lpWideCharStr, cchWideChar);
    v18 = lpWideCharStr;
  }
  else
  {
    lpWideCharStr = 0;
    v17 = MultiByteToWideChar(0, 0, (LPCCH)a2, cbMaxLen_low, WideCharStr, 1024);
    v18 = WideCharStr;
  }
  v20 = CPersistStreamInit::TextOutW(this, v18, v17, v14);
  if ( lpWideCharStr )
    MMMFree((unsigned __int8 *)lpWideCharStr);
LABEL_22:
  if ( v10 )
  {
    if ( !a5->dwMemOwner )
    {
      CoTaskMemFree(a2);
      *(_QWORD *)(a5->obValue + *((_QWORD *)a3 + 11)) = 0;
    }
  }
  return v20;
}

```

## disassembly

```asm
0x18001f5c4  mov     [rsp+arg_18], rbx
0x18001f5c9  push    rbp
0x18001f5ca  push    rsi
0x18001f5cb  push    rdi
0x18001f5cc  push    r12
0x18001f5ce  push    r13
0x18001f5d0  push    r14
0x18001f5d2  push    r15
0x18001f5d4  sub     rsp, 850h
0x18001f5db  mov     rax, cs:__security_cookie
0x18001f5e2  xor     rax, rsp
0x18001f5e5  mov     [rsp+888h+var_48], rax
0x18001f5ed  mov     rsi, [rsp+888h+arg_20]
0x18001f5f5  mov     r12, rcx
0x18001f5f8  mov     rdi, rdx
0x18001f5fb  mov     rcx, r8; this
0x18001f5fe  movzx   edx, r9w; unsigned __int16
0x18001f602  mov     r13, r8
0x18001f605  movzx   r10d, word ptr [rsi+54h]
0x18001f60a  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x18001f60f  bt      r10w, 0Eh
0x18001f615  movzx   r14d, ax
0x18001f619  jnb     short loc_18001F626
0x18001f61b  mov     rdi, [rdi]
0x18001f61e  mov     r15d, 1
0x18001f624  jmp     short loc_18001F629
0x18001f626  xor     r15d, r15d
0x18001f629  mov     rbx, [r13+58h]
0x18001f62d  mov     rax, [rsi+18h]
0x18001f631  cmp     dword ptr [rbx+rax], 4
0x18001f635  jnz     short loc_18001F64A
0x18001f637  mov     ebx, [rsi+48h]
0x18001f63a  cmp     rbx, [rsi+48h]
0x18001f63e  jz      short loc_18001F651
0x18001f640  mov     eax, 80004005h
0x18001f645  jmp     loc_18001F783
0x18001f64a  mov     rax, [rsi+10h]
0x18001f64e  mov     ebx, [rbx+rax]
0x18001f651  mov     eax, 0BFFFh
0x18001f656  and     r10w, ax
0x18001f65a  and     r14w, ax
0x18001f65e  mov     eax, 82h
0x18001f663  cmp     r10w, ax
0x18001f667  jnz     short loc_18001F682
0x18001f669  shr     ebx, 1
0x18001f66b  movzx   r9d, r14w; unsigned __int16
0x18001f66f  mov     r8d, ebx; unsigned int
0x18001f672  mov     rdx, rdi; unsigned __int16 *
0x18001f675  mov     rcx, r12; this
0x18001f678  call    ?TextOutW@CPersistStreamInit@@AEAAJPEAGKG@Z; CPersistStreamInit::TextOutW(ushort *,ulong,ushort)
0x18001f67d  jmp     loc_18001F75B
0x18001f682  mov     eax, 81h
0x18001f687  cmp     r10w, ax
0x18001f68b  jnz     loc_18001F74D
0x18001f691  lea     eax, [rbx+rbx]
0x18001f694  mov     ecx, 400h
0x18001f699  xor     edx, edx; dwFlags
0x18001f69b  mov     r9d, ebx; cbMultiByte
0x18001f69e  mov     r8, rdi; lpMultiByteStr
0x18001f6a1  cmp     eax, ecx
0x18001f6a3  jnb     short loc_18001F6C4
0x18001f6a5  mov     [rsp+888h+cchWideChar], ecx; cchWideChar
0x18001f6a9  lea     rax, [rsp+888h+WideCharStr]
0x18001f6ae  xor     ecx, ecx; CodePage
0x18001f6b0  mov     [rsp+888h+lpWideCharStr], rax; lpWideCharStr
0x18001f6b5  xor     ebp, ebp
0x18001f6b7  call    cs:__imp_MultiByteToWideChar
0x18001f6bd  lea     rdx, [rsp+888h+WideCharStr]
0x18001f6c2  jmp     short loc_18001F72D
0x18001f6c4  mov     [rsp+888h+cchWideChar], 0; cchWideChar
0x18001f6cc  xor     ecx, ecx; CodePage
0x18001f6ce  mov     [rsp+888h+lpWideCharStr], 0; lpWideCharStr
0x18001f6d7  call    cs:__imp_MultiByteToWideChar
0x18001f6dd  mov     [rsp+888h+var_858], eax
0x18001f6e1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f6e8  lea     edx, [rax+1]; unsigned int
0x18001f6eb  mov     eax, 2
0x18001f6f0  mul     rdx
0x18001f6f3  cmovb   rax, rcx
0x18001f6f7  mov     ecx, eax; unsigned int
0x18001f6f9  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18001f6fe  mov     rbp, rax
0x18001f701  test    rax, rax
0x18001f704  jnz     short loc_18001F70D
0x18001f706  mov     eax, 8007000Eh
0x18001f70b  jmp     short loc_18001F783
0x18001f70d  mov     eax, [rsp+888h+var_858]
0x18001f711  mov     r9d, ebx; cbMultiByte
0x18001f714  mov     [rsp+888h+cchWideChar], eax; cchWideChar
0x18001f718  mov     r8, rdi; lpMultiByteStr
0x18001f71b  xor     edx, edx; dwFlags
0x18001f71d  mov     [rsp+888h+lpWideCharStr], rbp; lpWideCharStr
0x18001f722  xor     ecx, ecx; CodePage
0x18001f724  call    cs:__imp_MultiByteToWideChar
0x18001f72a  mov     rdx, rbp; unsigned __int16 *
0x18001f72d  movzx   r9d, r14w; unsigned __int16
0x18001f731  mov     r8d, eax; unsigned int
0x18001f734  mov     rcx, r12; this
0x18001f737  call    ?TextOutW@CPersistStreamInit@@AEAAJPEAGKG@Z; CPersistStreamInit::TextOutW(ushort *,ulong,ushort)
0x18001f73c  mov     ebx, eax
0x18001f73e  test    rbp, rbp
0x18001f741  jz      short loc_18001F75D
0x18001f743  mov     rcx, rbp; unsigned __int8 *
0x18001f746  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18001f74b  jmp     short loc_18001F75D
0x18001f74d  mov     r8d, ebx; unsigned int
0x18001f750  mov     rdx, rdi; unsigned __int8 *
0x18001f753  mov     rcx, r12; this
0x18001f756  call    ?BinaryOut@CPersistStreamInit@@AEAAJPEAEK@Z; CPersistStreamInit::BinaryOut(uchar *,ulong)
0x18001f75b  mov     ebx, eax
0x18001f75d  test    r15d, r15d
0x18001f760  jz      short loc_18001F781
0x18001f762  cmp     dword ptr [rsi+3Ch], 0
0x18001f766  jnz     short loc_18001F781
0x18001f768  mov     rcx, rdi; pv
0x18001f76b  call    cs:__imp_CoTaskMemFree
0x18001f771  mov     rcx, [rsi+8]
0x18001f775  mov     rax, [r13+58h]
0x18001f779  mov     qword ptr [rcx+rax], 0
0x18001f781  mov     eax, ebx
0x18001f783  mov     rcx, [rsp+888h+var_48]
0x18001f78b  xor     rcx, rsp; StackCookie
0x18001f78e  call    __security_check_cookie
0x18001f793  mov     rbx, [rsp+888h+arg_18]
0x18001f79b  add     rsp, 850h
0x18001f7a2  pop     r15
0x18001f7a4  pop     r14
0x18001f7a6  pop     r13
0x18001f7a8  pop     r12
0x18001f7aa  pop     rdi
0x18001f7ab  pop     rsi
0x18001f7ac  pop     rbp
0x18001f7ad  retn
```
