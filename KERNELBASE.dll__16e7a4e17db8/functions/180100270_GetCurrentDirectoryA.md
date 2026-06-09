# GetCurrentDirectoryA

- ea: `0x180100270`
- end: `0x1801003f0`
- name: `GetCurrentDirectoryA`
- size: `384`
- prototype: `DWORD __stdcall(DWORD nBufferLength, LPSTR lpBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800134a0`
- `0x180100270`
- `0x180188f10`
- `0x180197010`

## import_xrefs

- `ntdll!RtlUnicodeToMultiByteSize` at `0x180100331`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x180100331`
- `ntdll!RtlFreeHeap` at `0x1801003e8`
- `ntdll!RtlFreeHeap` at `0x1801958d5`
- `ntdll!RtlFreeHeap` at `0x1801958f9`
- `ntdll!RtlFreeHeap` at `0x1801003e8`
- `ntdll!RtlFreeHeap` at `0x1801958d5`
- `ntdll!RtlFreeHeap` at `0x1801958f9`
- `ntdll!RtlGetCurrentDirectory_U` at `0x1801002c8`
- `ntdll!RtlGetCurrentDirectory_U` at `0x1801958ad`
- `ntdll!RtlGetCurrentDirectory_U` at `0x1801002c8`
- `ntdll!RtlGetCurrentDirectory_U` at `0x1801958ad`
- `ntdll!RtlAllocateHeap` at `0x1801003b6`
- `ntdll!RtlAllocateHeap` at `0x1801003b6`

## pseudocode

```c
DWORD __stdcall GetCurrentDirectoryA(DWORD nBufferLength, LPSTR lpBuffer)
{
  ULONG v2; // esi
  ULONG CurrentDirectory_U; // eax
  __int64 v5; // rcx
  ULONG v7; // edi
  WCHAR *v8; // rbx
  NTSTATUS v9; // eax
  DWORD v10; // edi
  WCHAR *Heap; // rax
  ULONG BytesInMultiByteString; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v13; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v14; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[128]; // [rsp+50h] [rbp-B0h] BYREF

  BytesInMultiByteString = 0;
  v2 = nBufferLength;
  if ( nBufferLength > 0xFFFD )
    v2 = 65533;
  v13 = 0;
  v14 = 0;
  CurrentDirectory_U = RtlGetCurrentDirectory_U(0x100u, Buffer);
  BytesInMultiByteString = CurrentDirectory_U;
  if ( !CurrentDirectory_U )
  {
LABEL_4:
    v5 = 3221225473LL;
LABEL_5:
    BaseSetLastNTError(v5);
    return 0;
  }
  v7 = CurrentDirectory_U + 2;
  if ( CurrentDirectory_U > 0x100 )
  {
    while ( v7 - 2 <= 0xFFFC )
    {
      Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      v8 = Heap;
      if ( !Heap )
      {
        v5 = 3221225495LL;
        goto LABEL_5;
      }
      CurrentDirectory_U = RtlGetCurrentDirectory_U(v7, Heap);
      BytesInMultiByteString = CurrentDirectory_U;
      if ( !CurrentDirectory_U )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
        goto LABEL_4;
      }
      if ( CurrentDirectory_U < v7 )
        goto LABEL_8;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
      v7 = BytesInMultiByteString + 2;
    }
    v5 = 3221225734LL;
    goto LABEL_5;
  }
  v8 = Buffer;
LABEL_8:
  LOWORD(v14) = CurrentDirectory_U;
  WORD1(v14) = v7;
  *((_QWORD *)&v14 + 1) = v8;
  v9 = RtlUnicodeToMultiByteSize(&BytesInMultiByteString, v8, (unsigned __int16)CurrentDirectory_U);
  if ( v9 < 0 )
    goto LABEL_11;
  if ( v2 <= BytesInMultiByteString )
  {
    v10 = BytesInMultiByteString + 1;
    goto LABEL_12;
  }
  WORD1(v13) = v2;
  LOWORD(v13) = 0;
  *((_QWORD *)&v13 + 1) = lpBuffer;
  v9 = ((__int64 (__fastcall *)(__int128 *, __int128 *, _QWORD))pfnUnicodeStringToEightBitString)(&v13, &v14, 0);
  if ( v9 >= 0 )
  {
    v10 = (unsigned __int16)v13;
  }
  else
  {
LABEL_11:
    BaseSetLastNTError((unsigned int)v9);
    v10 = 0;
  }
LABEL_12:
  if ( v8 != Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  return v10;
}

```

## disassembly

```asm
0x180100270  mov     [rsp-8+arg_10], rbx
0x180100275  mov     [rsp-8+arg_18], rsi
0x18010027a  push    rbp
0x18010027b  push    rdi
0x18010027c  push    r14
0x18010027e  lea     rbp, [rsp-60h]
0x180100283  sub     rsp, 160h
0x18010028a  mov     rax, cs:__security_cookie
0x180100291  xor     rax, rsp
0x180100294  mov     [rbp+70h+var_20], rax
0x180100298  mov     eax, 0FFFDh
0x18010029d  mov     [rsp+170h+BytesInMultiByteString], 0
0x1801002a5  cmp     ecx, eax
0x1801002a7  mov     esi, ecx
0x1801002a9  xorps   xmm0, xmm0
0x1801002ac  mov     r14, rdx
0x1801002af  mov     ebx, 100h
0x1801002b4  lea     rdx, [rsp+170h+Buffer]; Buffer
0x1801002b9  mov     ecx, ebx; MaximumLength
0x1801002bb  cmova   esi, eax
0x1801002be  movups  [rsp+170h+var_148], xmm0
0x1801002c3  movups  [rsp+170h+var_138], xmm0
0x1801002c8  call    cs:__imp_RtlGetCurrentDirectory_U
0x1801002ce  mov     [rsp+170h+BytesInMultiByteString], eax
0x1801002d2  test    eax, eax
0x1801002d4  jnz     short loc_180100306
0x1801002d6  mov     ecx, 0C0000001h
0x1801002db  call    BaseSetLastNTError
0x1801002e0  xor     eax, eax
0x1801002e2  mov     rcx, [rbp+70h+var_20]
0x1801002e6  xor     rcx, rsp; StackCookie
0x1801002e9  call    __security_check_cookie
0x1801002ee  lea     r11, [rsp+170h+var_10]
0x1801002f6  mov     rbx, [r11+30h]
0x1801002fa  mov     rsi, [r11+38h]
0x1801002fe  mov     rsp, r11
0x180100301  pop     r14
0x180100303  pop     rdi
0x180100304  pop     rbp
0x180100305  retn
0x180100306  lea     edi, [rax+2]
0x180100309  cmp     eax, ebx
0x18010030b  ja      loc_180100396
0x180100311  lea     rbx, [rsp+170h+Buffer]
0x180100316  movzx   r8d, ax; BytesInUnicodeString
0x18010031a  lea     rcx, [rsp+170h+BytesInMultiByteString]; BytesInMultiByteString
0x18010031f  mov     rdx, rbx; UnicodeString
0x180100322  mov     word ptr [rsp+170h+var_138], ax
0x180100327  mov     word ptr [rsp+170h+var_138+2], di
0x18010032c  mov     qword ptr [rsp+170h+var_138+8], rbx
0x180100331  call    cs:__imp_RtlUnicodeToMultiByteSize
0x180100337  test    eax, eax
0x180100339  js      short loc_180100375
0x18010033b  mov     edi, [rsp+170h+BytesInMultiByteString]
0x18010033f  cmp     esi, edi
0x180100341  jbe     loc_1801003D2
0x180100347  xor     eax, eax
0x180100349  mov     word ptr [rsp+170h+var_148+2], si
0x18010034e  mov     word ptr [rsp+170h+var_148], ax
0x180100353  lea     rdx, [rsp+170h+var_138]
0x180100358  mov     rax, cs:pfnUnicodeStringToEightBitString
0x18010035f  lea     rcx, [rsp+170h+var_148]
0x180100364  xor     r8d, r8d
0x180100367  mov     qword ptr [rsp+170h+var_148+8], r14
0x18010036c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100371  test    eax, eax
0x180100373  jns     short loc_18010038F
0x180100375  mov     ecx, eax
0x180100377  call    BaseSetLastNTError
0x18010037c  xor     edi, edi
0x18010037e  lea     rax, [rsp+170h+Buffer]
0x180100383  cmp     rbx, rax
0x180100386  jnz     short loc_1801003D6
0x180100388  mov     eax, edi
0x18010038a  jmp     loc_1801002E2
0x18010038f  movzx   edi, word ptr [rsp+170h+var_148]
0x180100394  jmp     short loc_18010037E
0x180100396  lea     eax, [rdi-2]
0x180100399  cmp     eax, 0FFFCh
0x18010039e  ja      loc_180195905
0x1801003a4  mov     rcx, gs:60h
0x1801003ad  xor     edx, edx; Flags
0x1801003af  mov     r8d, edi; Size
0x1801003b2  mov     rcx, [rcx+30h]; HeapHandle
0x1801003b6  call    cs:__imp_RtlAllocateHeap
0x1801003bc  mov     rbx, rax
0x1801003bf  test    rax, rax
0x1801003c2  jnz     loc_1801958A8
0x1801003c8  mov     ecx, 0C0000017h
0x1801003cd  jmp     loc_1801002DB
0x1801003d2  inc     edi
0x1801003d4  jmp     short loc_18010037E
0x1801003d6  mov     rcx, gs:60h
0x1801003df  mov     r8, rbx; P
0x1801003e2  xor     edx, edx; Flags
0x1801003e4  mov     rcx, [rcx+30h]; HeapHandle
0x1801003e8  call    cs:__imp_RtlFreeHeap
0x1801003ee  jmp     short loc_180100388
0x1801958a8  mov     rdx, rbx; Buffer
0x1801958ab  mov     ecx, edi; MaximumLength
0x1801958ad  call    cs:__imp_RtlGetCurrentDirectory_U
0x1801958b3  mov     [rsp+170h+BytesInMultiByteString], eax
0x1801958b7  test    eax, eax
0x1801958b9  jz      short loc_1801958E7
0x1801958bb  cmp     eax, edi
0x1801958bd  jb      loc_180100316
0x1801958c3  mov     rcx, gs:60h
0x1801958cc  mov     r8, rbx; P
0x1801958cf  xor     edx, edx; Flags
0x1801958d1  mov     rcx, [rcx+30h]; HeapHandle
0x1801958d5  call    cs:__imp_RtlFreeHeap
0x1801958db  mov     edi, [rsp+170h+BytesInMultiByteString]
0x1801958df  add     edi, 2
0x1801958e2  jmp     loc_180100396
0x1801958e7  mov     rcx, gs:60h
0x1801958f0  mov     r8, rbx; P
0x1801958f3  xor     edx, edx; Flags
0x1801958f5  mov     rcx, [rcx+30h]; HeapHandle
0x1801958f9  call    cs:__imp_RtlFreeHeap
0x1801958ff  nop
0x180195900  jmp     loc_1801002D6
0x180195905  mov     ecx, 0C0000106h
0x18019590a  jmp     loc_1801002DB
```
