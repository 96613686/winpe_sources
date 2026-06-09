# AssignAccessLetter(ushort const *,ushort *)

- ea: `0x14001cde8`
- end: `0x14001cf6c`
- name: `?AssignAccessLetter@@YAHPEBGPEAG@Z`
- size: `388`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140017044`
- `0x14001dedc`

## callees

- `0x14001cde8`
- `0x14001cf74`
- `0x14001d054`
- `0x14001d190`
- `0x14001d420`
- `0x14001d580`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001cf26`
- `KERNEL32!HeapFree` at `0x14001cf26`
- `KERNEL32!GetProcessHeap` at `0x14001cf18`
- `KERNEL32!GetProcessHeap` at `0x14001cf18`
- `KERNEL32!SetLastError` at `0x14001ceac`
- `KERNEL32!SetLastError` at `0x14001cf04`
- `KERNEL32!SetLastError` at `0x14001cf34`
- `KERNEL32!SetLastError` at `0x14001cf4f`
- `KERNEL32!SetLastError` at `0x14001ceac`
- `KERNEL32!SetLastError` at `0x14001cf04`
- `KERNEL32!SetLastError` at `0x14001cf34`
- `KERNEL32!SetLastError` at `0x14001cf4f`
- `KERNEL32!GetLastError` at `0x14001ce31`
- `KERNEL32!GetLastError` at `0x14001ce7a`
- `KERNEL32!GetLastError` at `0x14001ce9b`
- `KERNEL32!GetLastError` at `0x14001ceb7`
- `KERNEL32!GetLastError` at `0x14001cee0`
- `KERNEL32!GetLastError` at `0x14001cefa`
- `KERNEL32!GetLastError` at `0x14001cf0a`
- `KERNEL32!GetLastError` at `0x14001cf41`
- `KERNEL32!GetLastError` at `0x14001ce31`
- `KERNEL32!GetLastError` at `0x14001ce7a`
- `KERNEL32!GetLastError` at `0x14001ce9b`
- `KERNEL32!GetLastError` at `0x14001ceb7`
- `KERNEL32!GetLastError` at `0x14001cee0`
- `KERNEL32!GetLastError` at `0x14001cefa`
- `KERNEL32!GetLastError` at `0x14001cf0a`
- `KERNEL32!GetLastError` at `0x14001cf41`

## pseudocode

```c
__int64 __fastcall AssignAccessLetter(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  DWORD v3; // edi
  unsigned __int16 v4; // si
  unsigned int v6; // ebx
  void *FirstAccessPath; // r12
  unsigned int v8; // eax
  DWORD LastError; // edi
  unsigned int v10; // eax
  unsigned int v11; // eax
  HANDLE ProcessHeap; // rax
  BOOL v13; // r14d
  unsigned __int64 v15; // [rsp+68h] [rbp+48h] BYREF
  unsigned __int16 *v16; // [rsp+70h] [rbp+50h] BYREF

  v16 = 0;
  v15 = 0;
  v3 = 0;
  v4 = 0;
  v6 = 1;
  FirstAccessPath = FindFirstAccessPath(a1, (const unsigned __int16 **)&v16, &v15);
  if ( FirstAccessPath == (void *)-1LL )
  {
    if ( GetLastError() != 18 )
    {
      v6 = 0;
LABEL_26:
      LastError = GetLastError();
      goto LABEL_27;
    }
LABEL_18:
    LOWORD(v15) = *a2;
    v10 = AssignAccessLetter_AssignLetter(a1, &v15);
    if ( v6 )
    {
      v6 = v10;
      v3 = GetLastError();
    }
    v4 = v15;
LABEL_21:
    v11 = AssignAccessLetter_ClearAttributes(a1);
    if ( v6 )
    {
      v6 = v11;
      v3 = GetLastError();
    }
    SetLastError(v3);
    LastError = GetLastError();
    if ( FirstAccessPath == (void *)-1LL )
      goto LABEL_27;
    goto LABEL_24;
  }
  do
  {
    if ( v15 == 4 && v16[1] == 58 && v16[2] == 92 )
    {
      if ( *v16 == *a2 )
      {
        v4 = *a2;
      }
      else
      {
        v8 = DeleteAccessPath(v16, 4u);
        if ( v6 )
        {
          v6 = v8;
          v3 = GetLastError();
        }
      }
    }
  }
  while ( (unsigned int)FindNextAccessPath(FirstAccessPath, (const unsigned __int16 **)&v16, &v15) );
  if ( GetLastError() == 18 )
  {
    if ( v4 )
      goto LABEL_21;
    goto LABEL_18;
  }
  if ( v6 )
    v6 = 0;
  else
    SetLastError(v3);
  LastError = GetLastError();
LABEL_24:
  ProcessHeap = GetProcessHeap();
  v13 = HeapFree(ProcessHeap, 0, FirstAccessPath);
  SetLastError(6u);
  if ( v6 )
  {
    v6 = v13;
    goto LABEL_26;
  }
LABEL_27:
  *a2 = v4;
  SetLastError(LastError);
  return v6;
}

```

## disassembly

```asm
0x14001cde8  mov     [rsp-38h+arg_0], rbx
0x14001cded  push    rbp
0x14001cdee  push    rsi
0x14001cdef  push    rdi
0x14001cdf0  push    r12
0x14001cdf2  push    r13
0x14001cdf4  push    r14
0x14001cdf6  push    r15
0x14001cdf8  mov     rbp, rsp
0x14001cdfb  sub     rsp, 20h
0x14001cdff  xor     r13d, r13d
0x14001ce02  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x14001ce06  mov     r15, rdx
0x14001ce09  mov     [rbp+arg_10], r13
0x14001ce0d  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x14001ce11  mov     [rbp+arg_8], r13
0x14001ce15  mov     edi, r13d
0x14001ce18  mov     esi, r13d
0x14001ce1b  mov     r14, rcx
0x14001ce1e  mov     ebx, 1
0x14001ce23  call    ?FindFirstAccessPath@@YAPEAXPEBGPEAPEBGPEA_K@Z; FindFirstAccessPath(ushort const *,ushort const * *,unsigned __int64 *)
0x14001ce28  mov     r12, rax
0x14001ce2b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001ce2f  jnz     short loc_14001CE48
0x14001ce31  call    cs:__imp_GetLastError
0x14001ce37  cmp     eax, 12h
0x14001ce3a  jz      loc_14001CEC6
0x14001ce40  mov     ebx, r13d
0x14001ce43  jmp     loc_14001CF41
0x14001ce48  cmp     [rbp+arg_8], 4
0x14001ce4d  jnz     short loc_14001CE87
0x14001ce4f  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x14001ce53  cmp     word ptr [rcx+2], 3Ah ; ':'
0x14001ce58  jnz     short loc_14001CE87
0x14001ce5a  cmp     word ptr [rcx+4], 5Ch ; '\'
0x14001ce5f  jnz     short loc_14001CE87
0x14001ce61  movzx   eax, word ptr [r15]
0x14001ce65  cmp     [rcx], ax
0x14001ce68  jz      short loc_14001CE84
0x14001ce6a  mov     edx, 4; unsigned __int64
0x14001ce6f  call    ?DeleteAccessPath@@YAHPEBG_K@Z; DeleteAccessPath(ushort const *,unsigned __int64)
0x14001ce74  test    ebx, ebx
0x14001ce76  jz      short loc_14001CE87
0x14001ce78  mov     ebx, eax
0x14001ce7a  call    cs:__imp_GetLastError
0x14001ce80  mov     edi, eax
0x14001ce82  jmp     short loc_14001CE87
0x14001ce84  movzx   esi, ax
0x14001ce87  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x14001ce8b  mov     rcx, r12; void *
0x14001ce8e  lea     rdx, [rbp+arg_10]; unsigned __int16 **
0x14001ce92  call    ?FindNextAccessPath@@YAHPEAXPEAPEBGPEA_K@Z; FindNextAccessPath(void *,ushort const * *,unsigned __int64 *)
0x14001ce97  test    eax, eax
0x14001ce99  jnz     short loc_14001CE48
0x14001ce9b  call    cs:__imp_GetLastError
0x14001cea1  cmp     eax, 12h
0x14001cea4  jz      short loc_14001CEC1
0x14001cea6  test    ebx, ebx
0x14001cea8  jnz     short loc_14001CEB4
0x14001ceaa  mov     ecx, edi; dwErrCode
0x14001ceac  call    cs:__imp_SetLastError
0x14001ceb2  jmp     short loc_14001CEB7
0x14001ceb4  mov     ebx, r13d
0x14001ceb7  call    cs:__imp_GetLastError
0x14001cebd  mov     edi, eax
0x14001cebf  jmp     short loc_14001CF18
0x14001cec1  test    si, si
0x14001cec4  jnz     short loc_14001CEEC
0x14001cec6  movzx   eax, word ptr [r15]
0x14001ceca  lea     rdx, [rbp+arg_8]
0x14001cece  mov     rcx, r14
0x14001ced1  mov     word ptr [rbp+arg_8], ax
0x14001ced5  call    AssignAccessLetter_AssignLetter
0x14001ceda  test    ebx, ebx
0x14001cedc  jz      short loc_14001CEE8
0x14001cede  mov     ebx, eax
0x14001cee0  call    cs:__imp_GetLastError
0x14001cee6  mov     edi, eax
0x14001cee8  movzx   esi, word ptr [rbp+arg_8]
0x14001ceec  mov     rcx, r14
0x14001ceef  call    AssignAccessLetter_ClearAttributes
0x14001cef4  test    ebx, ebx
0x14001cef6  jz      short loc_14001CF02
0x14001cef8  mov     ebx, eax
0x14001cefa  call    cs:__imp_GetLastError
0x14001cf00  mov     edi, eax
0x14001cf02  mov     ecx, edi; dwErrCode
0x14001cf04  call    cs:__imp_SetLastError
0x14001cf0a  call    cs:__imp_GetLastError
0x14001cf10  mov     edi, eax
0x14001cf12  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x14001cf16  jz      short loc_14001CF49
0x14001cf18  call    cs:__imp_GetProcessHeap
0x14001cf1e  mov     r8, r12; lpMem
0x14001cf21  xor     edx, edx; dwFlags
0x14001cf23  mov     rcx, rax; hHeap
0x14001cf26  call    cs:__imp_HeapFree
0x14001cf2c  mov     ecx, 6; dwErrCode
0x14001cf31  mov     r14d, eax
0x14001cf34  call    cs:__imp_SetLastError
0x14001cf3a  test    ebx, ebx
0x14001cf3c  jz      short loc_14001CF49
0x14001cf3e  mov     ebx, r14d
0x14001cf41  call    cs:__imp_GetLastError
0x14001cf47  mov     edi, eax
0x14001cf49  mov     ecx, edi; dwErrCode
0x14001cf4b  mov     [r15], si
0x14001cf4f  call    cs:__imp_SetLastError
0x14001cf55  mov     eax, ebx
0x14001cf57  mov     rbx, [rsp+20h+arg_0]
0x14001cf5c  add     rsp, 20h
0x14001cf60  pop     r15
0x14001cf62  pop     r14
0x14001cf64  pop     r13
0x14001cf66  pop     r12
0x14001cf68  pop     rdi
0x14001cf69  pop     rsi
0x14001cf6a  pop     rbp
0x14001cf6b  retn
```
