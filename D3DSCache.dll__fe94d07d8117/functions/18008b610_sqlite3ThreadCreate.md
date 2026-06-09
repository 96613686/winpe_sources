# sqlite3ThreadCreate

- ea: `0x18008b610`
- end: `0x18008b6db`
- name: `sqlite3ThreadCreate`
- size: `203`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18009db54`
- `0x18009dc84`
- `0x18009e9c0`

## callees

- `0x180020d70`
- `0x180039f48`
- `0x18008b610`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008b684`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18008b684`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008b6b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008b6b2`

## pseudocode

```c
__int64 __fastcall sqlite3ThreadCreate(__int64 **a1, __int64 (__fastcall *a2)(__int64), __int64 a3)
{
  __int64 *v6; // rbx
  DWORD *v8; // rsi
  _QWORD *v9; // rdi
  __int64 v10; // rax

  *a1 = 0;
  v6 = (__int64 *)sqlite3Malloc(40);
  if ( !v6 )
    return 7;
  if ( !(_BYTE)word_1800C6974 || (unsigned int)sqlite3FaultSim(200) )
  {
    v9 = v6 + 2;
    v8 = (DWORD *)(v6 + 1);
  }
  else
  {
    v8 = (DWORD *)(v6 + 1);
    v6[3] = a3;
    v9 = v6 + 2;
    v6[2] = (__int64)a2;
    v10 = _o__beginthreadex(0, 0, sqlite3ThreadProc, v6, 0, v6 + 1);
    *v6 = v10;
    if ( v10 )
      goto LABEL_9;
  }
  *(_OWORD *)v6 = 0;
  *((_OWORD *)v6 + 1) = 0;
  v6[4] = 0;
LABEL_9:
  if ( !*v9 )
  {
    *v8 = GetCurrentThreadId();
    v6[4] = a2(a3);
  }
  *a1 = v6;
  return 0;
}

```

## disassembly

```asm
0x18008b610  push    rbx
0x18008b612  push    rbp
0x18008b613  push    rsi
0x18008b614  push    rdi
0x18008b615  push    r14
0x18008b617  push    r15
0x18008b619  sub     rsp, 38h
0x18008b61d  mov     r14, rcx
0x18008b620  mov     qword ptr [rcx], 0
0x18008b627  mov     ecx, 28h ; '('
0x18008b62c  mov     rbp, r8
0x18008b62f  mov     r15, rdx
0x18008b632  call    sqlite3Malloc
0x18008b637  mov     rbx, rax
0x18008b63a  test    rax, rax
0x18008b63d  jnz     short loc_18008B647
0x18008b63f  lea     eax, [rbx+7]
0x18008b642  jmp     loc_18008B6CE
0x18008b647  cmp     byte ptr cs:word_1800C6974, 0
0x18008b64e  jz      short loc_18008B694
0x18008b650  mov     ecx, 0C8h
0x18008b655  call    sqlite3FaultSim
0x18008b65a  test    eax, eax
0x18008b65c  jnz     short loc_18008B694
0x18008b65e  lea     rsi, [rbx+8]
0x18008b662  mov     [rbx+18h], rbp
0x18008b666  lea     rdi, [rbx+10h]
0x18008b66a  mov     [rsp+68h+var_40], rsi
0x18008b66f  mov     r9, rbx
0x18008b672  mov     [rsp+68h+var_48], eax
0x18008b676  lea     r8, sqlite3ThreadProc
0x18008b67d  mov     [rdi], r15
0x18008b680  xor     edx, edx
0x18008b682  xor     ecx, ecx
0x18008b684  call    cs:__imp__o__beginthreadex
0x18008b68a  mov     [rbx], rax
0x18008b68d  test    rax, rax
0x18008b690  jz      short loc_18008B69C
0x18008b692  jmp     short loc_18008B6AC
0x18008b694  lea     rdi, [rbx+10h]
0x18008b698  lea     rsi, [rbx+8]
0x18008b69c  xorps   xmm0, xmm0
0x18008b69f  xor     eax, eax
0x18008b6a1  movups  xmmword ptr [rbx], xmm0
0x18008b6a4  movups  xmmword ptr [rbx+10h], xmm0
0x18008b6a8  mov     [rbx+20h], rax
0x18008b6ac  cmp     qword ptr [rdi], 0
0x18008b6b0  jnz     short loc_18008B6C9
0x18008b6b2  call    cs:__imp_GetCurrentThreadId
0x18008b6b8  mov     [rsi], eax
0x18008b6ba  mov     rcx, rbp
0x18008b6bd  mov     rax, r15
0x18008b6c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b6c5  mov     [rbx+20h], rax
0x18008b6c9  mov     [r14], rbx
0x18008b6cc  xor     eax, eax
0x18008b6ce  add     rsp, 38h
0x18008b6d2  pop     r15
0x18008b6d4  pop     r14
0x18008b6d6  pop     rdi
0x18008b6d7  pop     rsi
0x18008b6d8  pop     rbp
0x18008b6d9  pop     rbx
0x18008b6da  retn
```
