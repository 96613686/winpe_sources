# AipAddPathMacro

- ea: `0x180004de4`
- end: `0x180004f44`
- name: `AipAddPathMacro`
- size: `352`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800028d0`
- `0x180004ca0`

## callees

- `0x180004de4`
- `0x180004f4c`
- `0x180005680`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180004e03`
- `ntdll!RtlEqualUnicodeString` at `0x180004e03`
- `ntdll!RtlFreeHeap` at `0x180004e6f`
- `ntdll!RtlFreeHeap` at `0x180004e9a`
- `ntdll!RtlFreeHeap` at `0x180004e6f`
- `ntdll!RtlFreeHeap` at `0x180004e9a`
- `ntdll!RtlAllocateHeap` at `0x180004e2a`
- `ntdll!RtlAllocateHeap` at `0x180004e2a`

## pseudocode

```c
__int64 __fastcall AipAddPathMacro(const UNICODE_STRING *a1, const UNICODE_STRING *a2, int a3)
{
  struct _UNICODE_STRING *v4; // rdi
  int v6; // esi
  int v7; // edx
  _QWORD *Heap; // rbx
  PWSTR Buffer; // r8
  _QWORD *v10; // rax
  struct _UNICODE_STRING v12; // [rsp+30h] [rbp-38h] BYREF

  v4 = (struct _UNICODE_STRING *)a2;
  v12 = 0;
  if ( RtlEqualUnicodeString(a1, a2, 1u) )
  {
    return (unsigned int)-1073741811;
  }
  else
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x38u);
    if ( Heap )
    {
      v6 = 0;
      if ( (a3 & 8) != 0 )
      {
        v6 = AipConvertToNtPath(v4, &v12);
        if ( v6 < 0 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
          return (unsigned int)v6;
        }
        Buffer = v4->Buffer;
        if ( v12.Buffer != Buffer )
        {
          if ( (a3 & 2) != 0 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
            v4->Buffer = 0;
          }
          a3 |= 2u;
          v4 = &v12;
        }
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_ZZ(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, (_DWORD)Buffer, (_DWORD)a1, (__int64)v4);
      *((_DWORD *)Heap + 4) = a3;
      *(UNICODE_STRING *)(Heap + 3) = *a1;
      if ( (a3 & 1) != 0 )
        a1->Buffer = 0;
      *(struct _UNICODE_STRING *)(Heap + 5) = *v4;
      if ( (a3 & 2) != 0 )
        v4->Buffer = 0;
      v10 = P;
      if ( *((PVOID **)P + 1) != &P )
        __fastfail(3u);
      *Heap = P;
      Heap[1] = &P;
      v10[1] = Heap;
      P = Heap;
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004de4  push    rbx
0x180004de6  push    rbp
0x180004de7  push    rsi
0x180004de8  push    rdi
0x180004de9  push    r14
0x180004deb  sub     rsp, 40h
0x180004def  mov     ebp, r8d
0x180004df2  xorps   xmm0, xmm0
0x180004df5  mov     r8b, 1; CaseInsensitive
0x180004df8  mov     rdi, rdx
0x180004dfb  movups  xmmword ptr [rsp+68h+var_38.Length], xmm0
0x180004e00  mov     r14, rcx
0x180004e03  call    cs:__imp_RtlEqualUnicodeString
0x180004e09  test    al, al
0x180004e0b  jz      short loc_180004E17
0x180004e0d  mov     esi, 0C000000Dh
0x180004e12  jmp     loc_180004F37
0x180004e17  mov     rcx, gs:60h
0x180004e20  xor     edx, edx; Flags
0x180004e22  mov     rcx, [rcx+30h]; HeapHandle
0x180004e26  lea     r8d, [rdx+38h]; Size
0x180004e2a  call    cs:__imp_RtlAllocateHeap
0x180004e30  mov     rbx, rax
0x180004e33  test    rax, rax
0x180004e36  jnz     short loc_180004E42
0x180004e38  mov     esi, 0C0000017h
0x180004e3d  jmp     loc_180004F37
0x180004e42  xor     esi, esi
0x180004e44  test    bpl, 8
0x180004e48  jz      short loc_180004EB0
0x180004e4a  lea     rdx, [rsp+68h+var_38]
0x180004e4f  mov     rcx, rdi
0x180004e52  call    AipConvertToNtPath
0x180004e57  mov     esi, eax
0x180004e59  test    eax, eax
0x180004e5b  jns     short loc_180004E7A
0x180004e5d  mov     rcx, gs:60h
0x180004e66  mov     r8, rbx; P
0x180004e69  xor     edx, edx; Flags
0x180004e6b  mov     rcx, [rcx+30h]; HeapHandle
0x180004e6f  call    cs:__imp_RtlFreeHeap
0x180004e75  jmp     loc_180004F37
0x180004e7a  mov     r8, [rdi+8]; P
0x180004e7e  cmp     [rsp+68h+var_38.Buffer], r8
0x180004e83  jz      short loc_180004EB0
0x180004e85  test    bpl, 2
0x180004e89  jz      short loc_180004EA8
0x180004e8b  mov     rcx, gs:60h
0x180004e94  xor     edx, edx; Flags
0x180004e96  mov     rcx, [rcx+30h]; HeapHandle
0x180004e9a  call    cs:__imp_RtlFreeHeap
0x180004ea0  mov     qword ptr [rdi+8], 0
0x180004ea8  or      ebp, 2
0x180004eab  lea     rdi, [rsp+68h+var_38]
0x180004eb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180004eb7  lea     rax, WPP_GLOBAL_Control
0x180004ebe  cmp     rcx, rax
0x180004ec1  jz      short loc_180004EDA
0x180004ec3  test    byte ptr [rcx+1Ch], 10h
0x180004ec7  jz      short loc_180004EDA
0x180004ec9  mov     rcx, [rcx+10h]
0x180004ecd  mov     r9, r14
0x180004ed0  mov     [rsp+68h+var_48], rdi
0x180004ed5  call    WPP_SF_ZZ
0x180004eda  mov     [rbx+10h], ebp
0x180004edd  movups  xmm0, xmmword ptr [r14]
0x180004ee1  movdqu  xmmword ptr [rbx+18h], xmm0
0x180004ee6  test    bpl, 1
0x180004eea  jz      short loc_180004EF4
0x180004eec  mov     qword ptr [r14+8], 0
0x180004ef4  movups  xmm0, xmmword ptr [rdi]
0x180004ef7  movdqu  xmmword ptr [rbx+28h], xmm0
0x180004efc  test    bpl, 2
0x180004f00  jz      short loc_180004F0A
0x180004f02  mov     qword ptr [rdi+8], 0
0x180004f0a  mov     rax, cs:P
0x180004f11  lea     rcx, P
0x180004f18  cmp     [rax+8], rcx
0x180004f1c  jz      short loc_180004F25
0x180004f1e  mov     ecx, 3
0x180004f23  int     29h; Win8: RtlFailFast(ecx)
0x180004f25  mov     [rbx], rax
0x180004f28  mov     [rbx+8], rcx
0x180004f2c  mov     [rax+8], rbx
0x180004f30  mov     cs:P, rbx
0x180004f37  mov     eax, esi
0x180004f39  add     rsp, 40h
0x180004f3d  pop     r14
0x180004f3f  pop     rdi
0x180004f40  pop     rsi
0x180004f41  pop     rbp
0x180004f42  pop     rbx
0x180004f43  retn
```
