# RegDeleteTreeW

- ea: `0x180050ee0`
- end: `0x180051184`
- name: `RegDeleteTreeW`
- size: `676`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180099814`
- `0x1800fa6bc`
- `0x180107150`
- `0x180121618`
- `0x18012b738`
- `0x180142770`
- `0x18016c5f0`

## callees

- `0x180050ee0`
- `0x180051430`
- `0x180051cc0`
- `0x18005b460`
- `0x18005b710`
- `0x1800a62a4`
- `0x18012d119`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180051058`
- `ntdll!RtlFreeUnicodeString` at `0x180051087`
- `ntdll!RtlFreeUnicodeString` at `0x1800510a0`
- `ntdll!RtlFreeUnicodeString` at `0x180051058`
- `ntdll!RtlFreeUnicodeString` at `0x180051087`
- `ntdll!RtlFreeUnicodeString` at `0x1800510a0`
- `ntdll!RtlCreateUnicodeString` at `0x180050f72`
- `ntdll!RtlCreateUnicodeString` at `0x18005111d`
- `ntdll!RtlCreateUnicodeString` at `0x180050f72`
- `ntdll!RtlCreateUnicodeString` at `0x18005111d`
- `ntdll!RtlFreeHeap` at `0x1800510b8`
- `ntdll!RtlFreeHeap` at `0x1800510d0`
- `ntdll!RtlFreeHeap` at `0x1800510b8`
- `ntdll!RtlFreeHeap` at `0x1800510d0`
- `ntdll!RtlAllocateHeap` at `0x180050f1a`
- `ntdll!RtlAllocateHeap` at `0x180050f4e`
- `ntdll!RtlAllocateHeap` at `0x180050f1a`
- `ntdll!RtlAllocateHeap` at `0x180050f4e`

## pseudocode

```c
LSTATUS __stdcall RegDeleteTreeW(HKEY hKey, LPCWSTR lpSubKey)
{
  char *Heap; // rax
  char *v5; // rsi
  WCHAR *v6; // r12
  LSTATUS v7; // edi
  int v8; // ebp
  LSTATUS v9; // eax
  __int64 v10; // rdx
  LSTATUS v11; // eax
  char *v12; // rbx
  struct _UNICODE_STRING *v13; // rcx
  __int64 v15; // r15
  DWORD cchName; // [rsp+90h] [rbp+18h] BYREF
  HKEY hKeya; // [rsp+98h] [rbp+20h] BYREF

  hKeya = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x3000u);
  v5 = Heap;
  if ( !Heap )
    return 8;
  memset_0(Heap, 0, 0x3000u);
  v6 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x202u);
  if ( v6 )
  {
    if ( !lpSubKey || !*lpSubKey || RtlCreateUnicodeString((PUNICODE_STRING)(v5 + 8), lpSubKey) )
    {
      v8 = 0;
      *(_QWORD *)v5 = hKey;
      v7 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          if ( v8 < 0 )
            goto LABEL_20;
          v7 = RegOpenKeyExInternalW(*(HKEY *)&v5[24 * v8], *(PCWSTR *)&v5[24 * v8 + 16], (PHANDLE)&hKeya, 0);
          if ( v7 )
            goto LABEL_18;
          cchName = 257;
          v9 = RegEnumKeyExW(hKeya, 0, v6, &cchName, 0, 0, 0, 0);
          v7 = v9;
          if ( v9 != 259 )
            break;
          v10 = *(_QWORD *)&v5[24 * v8 + 16];
          if ( v10 )
            v11 = RegDeleteKeyExInternalW(*(_QWORD *)&v5[24 * v8], v10, 0, 0, 0);
          else
            v11 = DeleteAllKeyValues(hKey);
          v7 = v11;
          RegCloseKey(hKeya);
          if ( v7 )
            goto LABEL_18;
          v12 = &v5[24 * v8];
          RtlFreeUnicodeString((PUNICODE_STRING)(v12 + 8));
          *(_OWORD *)(v12 + 8) = 0;
          if ( v8 > 0 )
          {
            RegCloseKey(*(HKEY *)&v5[24 * v8]);
            *(_QWORD *)&v5[24 * v8] = 0;
          }
          --v8;
        }
        if ( v9 )
          break;
        if ( v8 + 1 >= 512
          || (v15 = v8 + 1LL, v6[cchName] = 0, !RtlCreateUnicodeString((PUNICODE_STRING)&v5[24 * v15 + 8], v6)) )
        {
          RegCloseKey(hKeya);
          v7 = 8;
LABEL_18:
          while ( 1 )
          {
            v13 = (struct _UNICODE_STRING *)(v5 + 8);
            if ( v8 <= 0 )
              break;
            RtlFreeUnicodeString((struct _UNICODE_STRING *)((char *)v13 + 24 * (unsigned int)v8));
            RegCloseKey(*(HKEY *)&v5[24 * v8--]);
          }
          RtlFreeUnicodeString(v13);
          goto LABEL_20;
        }
        ++v8;
        *(_QWORD *)&v5[24 * v15] = hKeya;
      }
      RegCloseKey(hKeya);
      goto LABEL_18;
    }
    v7 = 8;
LABEL_20:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  }
  else
  {
    v7 = 8;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  return v7;
}

```

## disassembly

```asm
0x180050ee0  mov     rax, rsp
0x180050ee3  mov     [rax+8], rbx
0x180050ee7  push    rbp
0x180050ee8  push    rsi
0x180050ee9  push    rdi
0x180050eea  push    r12
0x180050eec  push    r13
0x180050eee  push    r14
0x180050ef0  push    r15
0x180050ef2  sub     rsp, 40h
0x180050ef6  mov     r13, rcx
0x180050ef9  mov     rbx, rdx
0x180050efc  xor     r15d, r15d
0x180050eff  mov     edi, 3000h
0x180050f04  mov     [rax+20h], r15
0x180050f08  mov     r8d, edi; Size
0x180050f0b  mov     rcx, gs:60h
0x180050f14  xor     edx, edx; Flags
0x180050f16  mov     rcx, [rcx+30h]; HeapHandle
0x180050f1a  call    cs:__imp_RtlAllocateHeap
0x180050f20  mov     rsi, rax
0x180050f23  test    rax, rax
0x180050f26  jz      loc_180051168
0x180050f2c  mov     r8d, edi; Size
0x180050f2f  xor     edx, edx; Val
0x180050f31  mov     rcx, rax; void *
0x180050f34  call    memset_0
0x180050f39  mov     rcx, gs:60h
0x180050f42  xor     edx, edx; Flags
0x180050f44  mov     r8d, 202h; Size
0x180050f4a  mov     rcx, [rcx+30h]; HeapHandle
0x180050f4e  call    cs:__imp_RtlAllocateHeap
0x180050f54  mov     r12, rax
0x180050f57  test    rax, rax
0x180050f5a  jz      loc_18005113A
0x180050f60  test    rbx, rbx
0x180050f63  jz      short loc_180050F85
0x180050f65  cmp     [rbx], r15w
0x180050f69  jz      short loc_180050F85
0x180050f6b  lea     rcx, [rsi+8]; DestinationString
0x180050f6f  mov     rdx, rbx; SourceString
0x180050f72  call    cs:__imp_RtlCreateUnicodeString
0x180050f78  test    al, al
0x180050f7a  jnz     short loc_180050F85
0x180050f7c  lea     edi, [r15+8]
0x180050f80  jmp     loc_1800510A6
0x180050f85  mov     ebp, r15d
0x180050f88  mov     [rsi], r13
0x180050f8b  mov     edi, r15d
0x180050f8e  test    ebp, ebp
0x180050f90  js      loc_1800510A6
0x180050f96  lea     rax, [rsp+78h+hKey]
0x180050f9e  movsxd  r15, ebp
0x180050fa1  xor     ebx, ebx
0x180050fa3  mov     r9d, 2000000h
0x180050fa9  mov     [rsp+78h+lpClass], rbx; __int64
0x180050fae  xor     r8d, r8d
0x180050fb1  mov     [rsp+78h+lpReserved], rax; PHANDLE
0x180050fb6  lea     r14, [r15+r15*2]
0x180050fba  mov     rdx, [rsi+r14*8+10h]; SourceString
0x180050fbf  mov     rcx, [rsi+r14*8]; hKey
0x180050fc3  call    RegOpenKeyExInternalW
0x180050fc8  mov     edi, eax
0x180050fca  test    eax, eax
0x180050fcc  jnz     loc_180051098
0x180050fd2  mov     rcx, [rsp+78h+hKey]; hKey
0x180050fda  lea     r9, [rsp+78h+cchName]; lpcchName
0x180050fe2  mov     [rsp+78h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x180050fe7  mov     r8, r12; lpName
0x180050fea  mov     [rsp+78h+lpcchClass], rbx; lpcchClass
0x180050fef  xor     edx, edx; dwIndex
0x180050ff1  mov     [rsp+78h+lpClass], rbx; lpClass
0x180050ff6  mov     [rsp+78h+lpReserved], rbx; lpReserved
0x180050ffb  mov     [rsp+78h+cchName], 101h
0x180051006  call    RegEnumKeyExW
0x18005100b  mov     edi, eax
0x18005100d  cmp     eax, 103h
0x180051012  jnz     loc_1800510F0
0x180051018  mov     rdx, [rsi+r14*8+10h]
0x18005101d  xor     r15d, r15d
0x180051020  test    rdx, rdx
0x180051023  jz      loc_180051144
0x180051029  mov     rcx, [rsi+r14*8]
0x18005102d  xor     r9d, r9d
0x180051030  xor     r8d, r8d
0x180051033  mov     [rsp+78h+lpReserved], r15
0x180051038  call    RegDeleteKeyExInternalW
0x18005103d  mov     rcx, [rsp+78h+hKey]; hKey
0x180051045  mov     edi, eax
0x180051047  call    RegCloseKey
0x18005104c  test    edi, edi
0x18005104e  jnz     short loc_180051098
0x180051050  lea     rbx, [rsi+r14*8]
0x180051054  lea     rcx, [rbx+8]; UnicodeString
0x180051058  call    cs:__imp_RtlFreeUnicodeString
0x18005105e  xorps   xmm0, xmm0
0x180051061  movups  xmmword ptr [rbx+8], xmm0
0x180051065  test    ebp, ebp
0x180051067  jle     short loc_180051076
0x180051069  mov     rcx, [rsi+r14*8]; hKey
0x18005106d  call    RegCloseKey
0x180051072  mov     [rsi+r14*8], r15
0x180051076  dec     ebp
0x180051078  jmp     loc_180050F8E
0x18005107d  mov     eax, ebp
0x18005107f  lea     rbx, [rax+rax*2]
0x180051083  lea     rcx, [rcx+rbx*8]; UnicodeString
0x180051087  call    cs:__imp_RtlFreeUnicodeString
0x18005108d  mov     rcx, [rsi+rbx*8]; hKey
0x180051091  call    RegCloseKey
0x180051096  dec     ebp
0x180051098  lea     rcx, [rsi+8]; UnicodeString
0x18005109c  test    ebp, ebp
0x18005109e  jg      short loc_18005107D
0x1800510a0  call    cs:__imp_RtlFreeUnicodeString
0x1800510a6  mov     rcx, gs:60h
0x1800510af  mov     r8, r12; P
0x1800510b2  xor     edx, edx; Flags
0x1800510b4  mov     rcx, [rcx+30h]; HeapHandle
0x1800510b8  call    cs:__imp_RtlFreeHeap
0x1800510be  mov     rcx, gs:60h
0x1800510c7  mov     r8, rsi; P
0x1800510ca  xor     edx, edx; Flags
0x1800510cc  mov     rcx, [rcx+30h]; HeapHandle
0x1800510d0  call    cs:__imp_RtlFreeHeap
0x1800510d6  mov     eax, edi
0x1800510d8  mov     rbx, [rsp+78h+arg_0]
0x1800510e0  add     rsp, 40h
0x1800510e4  pop     r15
0x1800510e6  pop     r14
0x1800510e8  pop     r13
0x1800510ea  pop     r12
0x1800510ec  pop     rdi
0x1800510ed  pop     rsi
0x1800510ee  pop     rbp
0x1800510ef  retn
0x1800510f0  test    eax, eax
0x1800510f2  jnz     short loc_180051172
0x1800510f4  lea     ebx, [rbp+1]
0x1800510f7  cmp     ebx, 200h
0x1800510fd  jge     short loc_180051151
0x1800510ff  mov     ecx, [rsp+78h+cchName]
0x180051106  inc     r15
0x180051109  mov     rdx, r12; SourceString
0x18005110c  mov     [r12+rcx*2], ax
0x180051111  lea     r14, [r15+r15*2]
0x180051115  lea     rcx, [rsi+8]
0x180051119  lea     rcx, [rcx+r14*8]; DestinationString
0x18005111d  call    cs:__imp_RtlCreateUnicodeString
0x180051123  test    al, al
0x180051125  jz      short loc_180051151
0x180051127  mov     rax, [rsp+78h+hKey]
0x18005112f  mov     ebp, ebx
0x180051131  mov     [rsi+r14*8], rax
0x180051135  jmp     loc_180050F8E
0x18005113a  mov     edi, 8
0x18005113f  jmp     loc_1800510BE
0x180051144  mov     rcx, r13; hKey
0x180051147  call    DeleteAllKeyValues
0x18005114c  jmp     loc_18005103D
0x180051151  mov     rcx, [rsp+78h+hKey]; hKey
0x180051159  call    RegCloseKey
0x18005115e  mov     edi, 8
0x180051163  jmp     loc_180051098
0x180051168  mov     eax, 8
0x18005116d  jmp     loc_1800510D8
0x180051172  mov     rcx, [rsp+78h+hKey]; hKey
0x18005117a  call    RegCloseKey
0x18005117f  jmp     loc_180051098
```
