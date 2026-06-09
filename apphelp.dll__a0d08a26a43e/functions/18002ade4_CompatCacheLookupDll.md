# CompatCacheLookupDll

- ea: `0x18002ade4`
- end: `0x18002b156`
- name: `CompatCacheLookupDll`
- size: `882`
- prototype: `__int64(_QWORD *, _DWORD *, WCHAR *, ...)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180034170`
- `0x1800509c0`
- `0x180050bc0`

## callees

- `0x18002ade4`
- `0x18002b15c`
- `0x18002b238`
- `0x180039a12`
- `0x180039a1e`
- `0x180039a36`
- `0x180039a42`
- `0x180059175`
- `0x18005a010`

## import_xrefs

- `ntdll!RtlDestroyEnvironment` at `0x18002b0cc`
- `ntdll!RtlDestroyEnvironment` at `0x18002b0cc`
- `ntdll!RtlSizeHeap` at `0x18002aed4`
- `ntdll!RtlSizeHeap` at `0x18002aed4`
- `ntdll!RtlSetEnvironmentVar` at `0x18002aea3`
- `ntdll!RtlSetEnvironmentVar` at `0x18002aea3`
- `ntdll!RtlCreateEnvironmentEx` at `0x18002ae75`
- `ntdll!RtlCreateEnvironmentEx` at `0x18002ae75`
- `ntdll!RtlFreeHeap` at `0x18002b109`
- `ntdll!RtlFreeHeap` at `0x18002b109`
- `ntdll!RtlAllocateHeap` at `0x18002af25`
- `ntdll!RtlAllocateHeap` at `0x18002af25`

## string_xrefs

- `0x18002ae91`: `__COMPAT_LAYER`

## pseudocode

```c
__int64 CompatCacheLookupDll(_QWORD *a1, _DWORD *a2, WCHAR *a3, ...)
{
  PVOID ProcessHeap; // r12
  NTSTATUS Environment; // ebx
  char *Heap; // rax
  char *v9; // rsi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rdx
  _DWORD *Heap_0; // rax
  _DWORD *v15; // rdi
  __int64 v16; // rdx
  _OWORD *v17; // rcx
  char *v18; // rax
  __int128 v19; // xmm1
  __int64 v20; // rdx
  _DWORD v22[6]; // [rsp+68h] [rbp-A0h] BYREF
  HANDLE v23; // [rsp+80h] [rbp-88h]
  __int16 v24; // [rsp+90h] [rbp-78h]
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-70h] BYREF
  PVOID v26; // [rsp+A8h] [rbp-60h]
  int v27; // [rsp+B0h] [rbp-58h]
  char *v28; // [rsp+1E0h] [rbp+D8h]
  int v29; // [rsp+1E8h] [rbp+E0h]
  HANDLE Handle; // [rsp+238h] [rbp+130h] BYREF
  PVOID MemoryPointer; // [rsp+240h] [rbp+138h] BYREF
  va_list MemoryPointera; // [rsp+240h] [rbp+138h]
  __int64 v33; // [rsp+248h] [rbp+140h]
  __int64 v34; // [rsp+250h] [rbp+148h]
  va_list va1; // [rsp+258h] [rbp+150h] BYREF

  va_start(va1, a3);
  va_start(MemoryPointera, a3);
  MemoryPointer = va_arg(va1, PVOID);
  v33 = va_arg(va1, _QWORD);
  v34 = va_arg(va1, _QWORD);
  memset_0(v22, 0, 0x188u);
  MemoryPointer = 0;
  Handle = 0;
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  if ( !a3 )
    return 3221225485LL;
  v22[0] = 1;
  v24 = -31132;
  Environment = RtlCreateEnvironmentEx(0, (PVOID *)MemoryPointera, 0);
  if ( Environment < 0 )
    goto LABEL_39;
  Environment = RtlSetEnvironmentVar((PVOID *)MemoryPointera, L"__COMPAT_LAYER", 14);
  if ( Environment < 0 )
    goto LABEL_39;
  v26 = MemoryPointer;
  v27 = RtlSizeHeap(NtCurrentPeb()->ProcessHeap, 0, MemoryPointer);
  Environment = RtlInitUnicodeStringEx_0(&DestinationString, a3);
  if ( Environment < 0 )
    goto LABEL_39;
  Environment = CompatCachepFileOpen(&Handle, a3);
  if ( Environment < 0 )
    goto LABEL_39;
  v23 = Handle;
  Heap = (char *)RtlAllocateHeap(ProcessHeap, 0, 0x1000u);
  v9 = Heap;
  if ( !Heap )
  {
    Environment = -1073741801;
LABEL_39:
    v9 = 0;
    goto LABEL_27;
  }
  memset_0(Heap, 0, 0x1000u);
  v28 = v9;
  v29 = 464;
  Environment = ((__int64 (__fastcall *)(_QWORD, _DWORD *))g_CompatCacheServiceApi)(0, v22);
  if ( Environment >= 0 )
  {
    v10 = 0;
    do
    {
      v11 = v10 + 8;
      if ( v10 + 8 >= v10 && v11 <= 0x1D0 )
      {
        v12 = *(_QWORD *)&v9[v10];
        v13 = v11 + HIDWORD(v12);
        if ( v13 >= v11 && v13 + 3 >= v13 )
        {
          v10 = (v13 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
          if ( v10 <= 0x1D0 )
            continue;
        }
      }
      goto LABEL_26;
    }
    while ( (_DWORD)v12 != 1 );
    if ( HIDWORD(v12) != 456 )
    {
LABEL_26:
      Environment = -1073741275;
      goto LABEL_27;
    }
    Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 8u, 0x1C8u);
    v15 = Heap_0;
    if ( Heap_0 )
    {
      v16 = 3;
      v17 = Heap_0;
      v18 = &v9[v11];
      do
      {
        *v17 = *(_OWORD *)v18;
        v17[1] = *((_OWORD *)v18 + 1);
        v17[2] = *((_OWORD *)v18 + 2);
        v17[3] = *((_OWORD *)v18 + 3);
        v17[4] = *((_OWORD *)v18 + 4);
        v17[5] = *((_OWORD *)v18 + 5);
        v17[6] = *((_OWORD *)v18 + 6);
        v19 = *((_OWORD *)v18 + 7);
        v18 += 128;
        v17[7] = v19;
        v17 += 8;
        --v16;
      }
      while ( v16 );
      v20 = (unsigned int)v34;
      *v17 = *(_OWORD *)v18;
      v17[1] = *((_OWORD *)v18 + 1);
      v17[2] = *((_OWORD *)v18 + 2);
      v17[3] = *((_OWORD *)v18 + 3);
      *((_QWORD *)v17 + 8) = *((_QWORD *)v18 + 8);
      CompatCachepFilterByCallerComponent(v15, v20, 128);
      if ( v15[42] )
      {
        if ( a1 )
        {
          *a1 = v15;
          v15 = 0;
        }
        if ( a2 )
          *a2 = 456;
        Environment = 0;
        if ( !v15 )
          goto LABEL_27;
      }
      else
      {
        Environment = -1073741275;
      }
      RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v15);
    }
    else
    {
      Environment = -1073741801;
    }
  }
LABEL_27:
  if ( MemoryPointer )
    RtlDestroyEnvironment((PWSTR)MemoryPointer);
  if ( Handle )
    NtClose_0(Handle);
  if ( v9 )
    RtlFreeHeap(ProcessHeap, 0, v9);
  return (unsigned int)Environment;
}

```

## disassembly

```asm
0x18002ade4  mov     rax, rsp
0x18002ade7  mov     [rax+8], rbx
0x18002adeb  mov     [rax+10h], rsi
0x18002adef  mov     [rax+20h], r9
0x18002adf3  push    rbp
0x18002adf4  push    rdi
0x18002adf5  push    r12
0x18002adf7  push    r14
0x18002adf9  push    r15
0x18002adfb  lea     rbp, [rax-118h]
0x18002ae02  sub     rsp, 1F0h
0x18002ae09  mov     rdi, r8
0x18002ae0c  mov     r14, rdx
0x18002ae0f  mov     r15, rcx
0x18002ae12  xor     edx, edx; Val
0x18002ae14  mov     r8d, 188h; Size
0x18002ae1a  lea     rcx, [rsp+210h+var_1B0]; void *
0x18002ae1f  call    memset_0
0x18002ae24  mov     [rbp+110h+MemoryPointer], 0
0x18002ae2f  xorps   xmm0, xmm0
0x18002ae32  mov     [rbp+110h+Handle], 0
0x18002ae3d  mov     rax, gs:60h
0x18002ae46  movups  [rsp+210h+var_1C8+8], xmm0
0x18002ae4b  mov     r12, [rax+30h]
0x18002ae4f  test    rdi, rdi
0x18002ae52  jz      loc_18002B118
0x18002ae58  mov     eax, 8664h
0x18002ae5d  mov     [rsp+210h+var_1B0], 1
0x18002ae65  xor     r8d, r8d
0x18002ae68  mov     [rbp+110h+var_188], ax
0x18002ae6c  lea     rdx, [rbp+110h+MemoryPointer]
0x18002ae73  xor     ecx, ecx
0x18002ae75  call    cs:__imp_RtlCreateEnvironmentEx
0x18002ae7b  mov     ebx, eax
0x18002ae7d  test    eax, eax
0x18002ae7f  js      loc_18002B14C
0x18002ae85  xor     r9d, r9d
0x18002ae88  mov     [rsp+210h+var_1F0], 0
0x18002ae91  lea     rdx, aCompatLayer; "__COMPAT_LAYER"
0x18002ae98  lea     rcx, [rbp+110h+MemoryPointer]
0x18002ae9f  lea     r8d, [r9+0Eh]
0x18002aea3  call    cs:__imp_RtlSetEnvironmentVar
0x18002aea9  mov     ebx, eax
0x18002aeab  test    eax, eax
0x18002aead  js      loc_18002B14C
0x18002aeb3  mov     rax, [rbp+110h+MemoryPointer]
0x18002aeba  xor     edx, edx; Flags
0x18002aebc  mov     [rbp+110h+var_170], rax
0x18002aec0  mov     rcx, gs:60h
0x18002aec9  mov     r8, [rbp+110h+MemoryPointer]; MemoryPointer
0x18002aed0  mov     rcx, [rcx+30h]; HeapHandle
0x18002aed4  call    cs:__imp_RtlSizeHeap
0x18002aeda  mov     rdx, rdi; SourceString
0x18002aedd  lea     rcx, [rbp+110h+DestinationString]; DestinationString
0x18002aee1  mov     [rbp+110h+var_168], eax
0x18002aee4  call    RtlInitUnicodeStringEx_0
0x18002aee9  mov     ebx, eax
0x18002aeeb  test    eax, eax
0x18002aeed  js      loc_18002B14C
0x18002aef3  mov     rdx, rdi; FileName
0x18002aef6  lea     rcx, [rbp+110h+Handle]; FileHandle
0x18002aefd  call    CompatCachepFileOpen
0x18002af02  mov     ebx, eax
0x18002af04  test    eax, eax
0x18002af06  js      loc_18002B14C
0x18002af0c  mov     rax, [rbp+110h+Handle]
0x18002af13  mov     ebx, 1000h
0x18002af18  mov     r8d, ebx; Size
0x18002af1b  mov     [rsp+210h+var_198], rax
0x18002af20  xor     edx, edx; Flags
0x18002af22  mov     rcx, r12; HeapHandle
0x18002af25  call    cs:__imp_RtlAllocateHeap
0x18002af2b  mov     rsi, rax
0x18002af2e  test    rax, rax
0x18002af31  jz      loc_18002B147
0x18002af37  mov     r8d, ebx; Size
0x18002af3a  xor     edx, edx; Val
0x18002af3c  mov     rcx, rax; void *
0x18002af3f  call    memset_0
0x18002af44  mov     rax, cs:g_CompatCacheServiceApi
0x18002af4b  lea     rdx, [rsp+210h+var_1B0]
0x18002af50  mov     edi, 1D0h
0x18002af55  mov     [rbp+110h+var_38], rsi
0x18002af5c  xor     ecx, ecx
0x18002af5e  mov     [rbp+110h+var_30], edi
0x18002af64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af69  mov     ebx, eax
0x18002af6b  test    eax, eax
0x18002af6d  js      loc_18002B0C0
0x18002af73  xor     ecx, ecx
0x18002af75  cmp     rcx, rdi
0x18002af78  ja      loc_18002B0BB
0x18002af7e  lea     rbx, [rcx+8]
0x18002af82  cmp     rbx, rcx
0x18002af85  jb      loc_18002B0BB
0x18002af8b  cmp     rbx, rdi
0x18002af8e  ja      loc_18002B0BB
0x18002af94  mov     rax, [rcx+rsi]
0x18002af98  mov     rdx, rax
0x18002af9b  shr     rdx, 20h
0x18002af9f  add     rdx, rbx
0x18002afa2  cmp     rdx, rbx
0x18002afa5  jb      loc_18002B0BB
0x18002afab  lea     rcx, [rdx+3]
0x18002afaf  cmp     rcx, rdx
0x18002afb2  jb      loc_18002B0BB
0x18002afb8  and     rcx, 0FFFFFFFFFFFFFFFCh
0x18002afbc  cmp     rcx, rdi
0x18002afbf  ja      loc_18002B0BB
0x18002afc5  cmp     eax, 1
0x18002afc8  jnz     short loc_18002AF75
0x18002afca  shr     rax, 20h
0x18002afce  mov     edx, 1C8h
0x18002afd3  cmp     eax, edx
0x18002afd5  jnz     loc_18002B0BB
0x18002afdb  mov     rcx, gs:60h
0x18002afe4  mov     r8d, edx; Size
0x18002afe7  mov     edx, 8; Flags
0x18002afec  mov     rcx, [rcx+30h]; HeapHandle
0x18002aff0  call    RtlAllocateHeap_0
0x18002aff5  mov     rdi, rax
0x18002aff8  test    rax, rax
0x18002affb  jz      loc_18002B11F
0x18002b001  mov     edx, 3
0x18002b006  mov     rcx, rax
0x18002b009  lea     rax, [rbx+rsi]
0x18002b00d  lea     r8d, [rdx+7Dh]
0x18002b011  movups  xmm0, xmmword ptr [rax]
0x18002b014  movups  xmmword ptr [rcx], xmm0
0x18002b017  movups  xmm1, xmmword ptr [rax+10h]
0x18002b01b  movups  xmmword ptr [rcx+10h], xmm1
0x18002b01f  movups  xmm0, xmmword ptr [rax+20h]
0x18002b023  movups  xmmword ptr [rcx+20h], xmm0
0x18002b027  movups  xmm1, xmmword ptr [rax+30h]
0x18002b02b  movups  xmmword ptr [rcx+30h], xmm1
0x18002b02f  movups  xmm0, xmmword ptr [rax+40h]
0x18002b033  movups  xmmword ptr [rcx+40h], xmm0
0x18002b037  movups  xmm1, xmmword ptr [rax+50h]
0x18002b03b  movups  xmmword ptr [rcx+50h], xmm1
0x18002b03f  movups  xmm0, xmmword ptr [rax+60h]
0x18002b043  movups  xmmword ptr [rcx+60h], xmm0
0x18002b047  movups  xmm1, xmmword ptr [rax+70h]
0x18002b04b  add     rax, r8
0x18002b04e  movups  xmmword ptr [rcx+70h], xmm1
0x18002b052  add     rcx, r8
0x18002b055  sub     rdx, 1
0x18002b059  jnz     short loc_18002B011
0x18002b05b  movups  xmm0, xmmword ptr [rax]
0x18002b05e  mov     edx, dword ptr [rbp+110h+arg_28]
0x18002b064  movups  xmmword ptr [rcx], xmm0
0x18002b067  movups  xmm1, xmmword ptr [rax+10h]
0x18002b06b  movups  xmmword ptr [rcx+10h], xmm1
0x18002b06f  movups  xmm0, xmmword ptr [rax+20h]
0x18002b073  movups  xmmword ptr [rcx+20h], xmm0
0x18002b077  movups  xmm1, xmmword ptr [rax+30h]
0x18002b07b  movups  xmmword ptr [rcx+30h], xmm1
0x18002b07f  mov     rax, [rax+40h]
0x18002b083  mov     [rcx+40h], rax
0x18002b087  mov     rcx, rdi
0x18002b08a  call    CompatCachepFilterByCallerComponent
0x18002b08f  cmp     dword ptr [rdi+0A8h], 0
0x18002b096  jz      loc_18002B126
0x18002b09c  test    r15, r15
0x18002b09f  jz      short loc_18002B0A6
0x18002b0a1  mov     [r15], rdi
0x18002b0a4  xor     edi, edi
0x18002b0a6  test    r14, r14
0x18002b0a9  jz      short loc_18002B0B2
0x18002b0ab  mov     dword ptr [r14], 1C8h
0x18002b0b2  xor     ebx, ebx
0x18002b0b4  test    rdi, rdi
0x18002b0b7  jz      short loc_18002B0C0
0x18002b0b9  jmp     short loc_18002B12B
0x18002b0bb  mov     ebx, 0C0000225h
0x18002b0c0  mov     rcx, [rbp+110h+MemoryPointer]; Environment
0x18002b0c7  test    rcx, rcx
0x18002b0ca  jz      short loc_18002B0D2
0x18002b0cc  call    cs:__imp_RtlDestroyEnvironment
0x18002b0d2  mov     rcx, [rbp+110h+Handle]; Handle
0x18002b0d9  test    rcx, rcx
0x18002b0dc  jnz     short loc_18002B111
0x18002b0de  test    rsi, rsi
0x18002b0e1  jnz     short loc_18002B101
0x18002b0e3  mov     eax, ebx
0x18002b0e5  lea     r11, [rsp+210h+var_20]
0x18002b0ed  mov     rbx, [r11+30h]
0x18002b0f1  mov     rsi, [r11+38h]
0x18002b0f5  mov     rsp, r11
0x18002b0f8  pop     r15
0x18002b0fa  pop     r14
0x18002b0fc  pop     r12
0x18002b0fe  pop     rdi
0x18002b0ff  pop     rbp
0x18002b100  retn
0x18002b101  mov     r8, rsi; P
0x18002b104  xor     edx, edx; Flags
0x18002b106  mov     rcx, r12; HeapHandle
0x18002b109  call    cs:__imp_RtlFreeHeap
0x18002b10f  jmp     short loc_18002B0E3
0x18002b111  call    NtClose_0
0x18002b116  jmp     short loc_18002B0DE
0x18002b118  mov     eax, 0C000000Dh
0x18002b11d  jmp     short loc_18002B0E5
0x18002b11f  mov     ebx, 0C0000017h
0x18002b124  jmp     short loc_18002B0C0
0x18002b126  mov     ebx, 0C0000225h
0x18002b12b  mov     rcx, gs:60h
0x18002b134  mov     r8, rdi; P
0x18002b137  xor     edx, edx; Flags
0x18002b139  mov     rcx, [rcx+30h]; HeapHandle
0x18002b13d  call    RtlFreeHeap_0
0x18002b142  jmp     loc_18002B0C0
0x18002b147  mov     ebx, 0C0000017h
0x18002b14c  mov     rsi, qword ptr [rsp+210h+var_1B8]
0x18002b151  jmp     loc_18002B0C0
```
