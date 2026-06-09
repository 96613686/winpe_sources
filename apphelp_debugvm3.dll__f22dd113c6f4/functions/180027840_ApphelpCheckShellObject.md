# ApphelpCheckShellObject

- ea: `0x180027840`
- end: `0x180027a49`
- name: `ApphelpCheckShellObject`
- size: `521`
- prototype: `BOOL __stdcall(const IID *const ObjectCLSID, BOOL bShimIfNecessary, ULONGLONG *pullFlags)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000f114`
- `0x180027840`
- `0x180027a50`
- `0x1800280f0`
- `0x1800281ac`
- `0x180034170`

## import_xrefs

- `ntdll!LdrGetDllHandle` at `0x180027931`
- `ntdll!LdrGetDllHandle` at `0x180027931`
- `ntdll!RtlFreeHeap` at `0x18002794d`
- `ntdll!RtlFreeHeap` at `0x1800279d3`
- `ntdll!RtlFreeHeap` at `0x18002794d`
- `ntdll!RtlFreeHeap` at `0x1800279d3`
- `ntdll!RtlAllocateHeap` at `0x1800278b5`
- `ntdll!RtlAllocateHeap` at `0x1800279ee`
- `ntdll!RtlAllocateHeap` at `0x1800278b5`
- `ntdll!RtlAllocateHeap` at `0x1800279ee`
- `ntdll!RtlInitUnicodeStringEx` at `0x180027912`
- `ntdll!RtlInitUnicodeStringEx` at `0x180027912`

## string_xrefs

- `0x180027a29`: `Failed to initialize dll name.`

## pseudocode

```c
BOOL __stdcall ApphelpCheckShellObject(const IID *const ObjectCLSID, BOOL bShimIfNecessary, ULONGLONG *pullFlags)
{
  char v3; // al
  int v7; // edi
  char *Heap; // rsi
  unsigned int v10; // eax
  SIZE_T v11; // rbp
  char *i; // rcx
  wchar_t *v13; // rbx
  __int64 v14; // r8
  unsigned int v15; // ebx
  unsigned int v16; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF
  PVOID DllHandle; // [rsp+A8h] [rbp+20h] BYREF

  DllHandle = 0;
  DestinationString = 0;
  v3 = gdwInfrastructureFlags;
  if ( gdwInfrastructureFlags >= 0 )
    v3 = CheckAppcompatInfrastructureFlags();
  v7 = 1;
  if ( (v3 & 1) == 0 )
  {
    if ( pullFlags )
      *pullFlags = 0;
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
    if ( Heap )
    {
      v10 = ResolveCOMServer((GUID *)ObjectCLSID);
      v11 = v10;
      if ( !v10 )
        goto LABEL_17;
      if ( v10 <= 0x208 )
        goto LABEL_10;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v11);
      if ( Heap )
      {
        v15 = v11;
        v16 = ResolveCOMServer((GUID *)ObjectCLSID);
        LODWORD(v11) = v16;
        if ( v16 <= v15 && v16 )
        {
LABEL_10:
          for ( i = &Heap[2 * ((unsigned __int64)(unsigned int)v11 >> 1) - 2];
                i >= Heap && *(_WORD *)i != 92 && *(_WORD *)i != 47;
                i -= 2 )
          {
            ;
          }
          v13 = (wchar_t *)(i + 2);
          if ( RtlInitUnicodeStringEx(&DestinationString, (PCWSTR)i + 1) < 0 )
          {
            AslLogCallPrintf(1, "ApphelpCheckShellObject", 656, "Failed to initialize dll name.");
          }
          else if ( LdrGetDllHandle(0, 0, &DestinationString, &DllHandle) < 0
                 && (unsigned int)CompatCachepLookupCdb(v13) )
          {
            v7 = ApphelpCheckModule((_DWORD)Heap, 0, bShimIfNecessary, 0, 0, 1, 32);
          }
          goto LABEL_17;
        }
        AslLogCallPrintf(1, "ApphelpCheckShellObject", 628, "Memory allocation error");
LABEL_17:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        return v7;
      }
      v14 = 614;
    }
    else
    {
      v14 = 592;
    }
    AslLogCallPrintf(1, "ApphelpCheckShellObject", v14, "Memory allocation error");
  }
  return v7;
}

```

## disassembly

```asm
0x180027840  mov     rax, rsp
0x180027843  push    rbx
0x180027844  push    rbp
0x180027845  push    rsi
0x180027846  push    rdi
0x180027847  push    r14
0x180027849  push    r15
0x18002784b  sub     rsp, 58h
0x18002784f  xorps   xmm0, xmm0
0x180027852  mov     qword ptr [rax+20h], 0
0x18002785a  movups  xmmword ptr [rax-48h], xmm0
0x18002785e  mov     eax, cs:gdwInfrastructureFlags
0x180027864  mov     rbx, r8
0x180027867  mov     r15d, edx
0x18002786a  mov     r14, rcx
0x18002786d  test    eax, eax
0x18002786f  jns     loc_18002798F
0x180027875  mov     edi, 1
0x18002787a  and     eax, edi
0x18002787c  test    eax, eax
0x18002787e  jz      short loc_18002788F
0x180027880  mov     eax, edi
0x180027882  add     rsp, 58h
0x180027886  pop     r15
0x180027888  pop     r14
0x18002788a  pop     rdi
0x18002788b  pop     rsi
0x18002788c  pop     rbp
0x18002788d  pop     rbx
0x18002788e  retn
0x18002788f  test    rbx, rbx
0x180027892  jz      short loc_18002789B
0x180027894  mov     qword ptr [rbx], 0
0x18002789b  mov     rcx, gs:60h
0x1800278a4  mov     ebx, 208h
0x1800278a9  mov     r8d, ebx; Size
0x1800278ac  mov     edx, 8; Flags
0x1800278b1  mov     rcx, [rcx+30h]; HeapHandle
0x1800278b5  call    cs:__imp_RtlAllocateHeap
0x1800278bb  mov     rsi, rax
0x1800278be  test    rax, rax
0x1800278c1  jz      loc_180027999
0x1800278c7  mov     r8d, ebx
0x1800278ca  mov     rdx, rax
0x1800278cd  mov     rcx, r14; Guid
0x1800278d0  call    ResolveCOMServer
0x1800278d5  mov     ebp, eax
0x1800278d7  test    eax, eax
0x1800278d9  jz      short loc_18002793B
0x1800278db  cmp     ebp, ebx
0x1800278dd  ja      loc_1800279C1
0x1800278e3  mov     ecx, ebp
0x1800278e5  shr     rcx, 1
0x1800278e8  dec     rcx
0x1800278eb  lea     rcx, [rsi+rcx*2]
0x1800278ef  jmp     short loc_180027901
0x1800278f1  cmp     word ptr [rcx], 5Ch ; '\'
0x1800278f5  jz      short loc_180027906
0x1800278f7  cmp     word ptr [rcx], 2Fh ; '/'
0x1800278fb  jz      short loc_180027906
0x1800278fd  sub     rcx, 2
0x180027901  cmp     rcx, rsi
0x180027904  jnb     short loc_1800278F1
0x180027906  lea     rbx, [rcx+2]
0x18002790a  mov     rdx, rbx; SourceString
0x18002790d  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x180027912  call    cs:__imp_RtlInitUnicodeStringEx
0x180027918  test    eax, eax
0x18002791a  js      loc_180027A29
0x180027920  lea     r9, [rsp+88h+DllHandle]; DllHandle
0x180027928  xor     edx, edx; DllCharacteristics
0x18002792a  lea     r8, [rsp+88h+DestinationString]; DllName
0x18002792f  xor     ecx, ecx; DllPath
0x180027931  call    cs:__imp_LdrGetDllHandle
0x180027937  test    eax, eax
0x180027939  js      short loc_180027958
0x18002793b  mov     rcx, gs:60h
0x180027944  mov     r8, rsi; P
0x180027947  xor     edx, edx; Flags
0x180027949  mov     rcx, [rcx+30h]; HeapHandle
0x18002794d  call    cs:__imp_RtlFreeHeap
0x180027953  jmp     loc_180027880
0x180027958  mov     ebp, 20h ; ' '
0x18002795d  mov     rcx, rbx; Str
0x180027960  mov     edx, ebp
0x180027962  call    CompatCachepLookupCdb
0x180027967  test    eax, eax
0x180027969  jz      short loc_18002793B
0x18002796b  mov     [rsp+88h+var_58], ebp
0x18002796f  xor     r9d, r9d
0x180027972  mov     [rsp+88h+var_60], edi
0x180027976  mov     r8d, r15d
0x180027979  xor     edx, edx
0x18002797b  mov     [rsp+88h+var_68], 0
0x180027983  mov     rcx, rsi
0x180027986  call    ApphelpCheckModule
0x18002798b  mov     edi, eax
0x18002798d  jmp     short loc_18002793B
0x18002798f  call    CheckAppcompatInfrastructureFlags
0x180027994  jmp     loc_180027875
0x180027999  mov     r8d, 250h
0x18002799f  jmp     short loc_1800279A7
0x1800279a1  mov     r8d, 266h
0x1800279a7  lea     r9, aMemoryAllocati; "Memory allocation error"
0x1800279ae  mov     ecx, edi
0x1800279b0  lea     rdx, aApphelpchecksh_0; "ApphelpCheckShellObject"
0x1800279b7  call    AslLogCallPrintf
0x1800279bc  jmp     loc_180027880
0x1800279c1  mov     rcx, gs:60h
0x1800279ca  mov     r8, rsi; P
0x1800279cd  xor     edx, edx; Flags
0x1800279cf  mov     rcx, [rcx+30h]; HeapHandle
0x1800279d3  call    cs:__imp_RtlFreeHeap
0x1800279d9  mov     rcx, gs:60h
0x1800279e2  mov     r8, rbp; Size
0x1800279e5  mov     edx, 8; Flags
0x1800279ea  mov     rcx, [rcx+30h]; HeapHandle
0x1800279ee  call    cs:__imp_RtlAllocateHeap
0x1800279f4  mov     rsi, rax
0x1800279f7  test    rax, rax
0x1800279fa  jz      short loc_1800279A1
0x1800279fc  mov     r8d, ebp
0x1800279ff  mov     rdx, rax
0x180027a02  mov     rcx, r14; Guid
0x180027a05  mov     ebx, ebp
0x180027a07  call    ResolveCOMServer
0x180027a0c  mov     ebp, eax
0x180027a0e  cmp     eax, ebx
0x180027a10  ja      short loc_180027A1A
0x180027a12  test    eax, eax
0x180027a14  jnz     loc_1800278E3
0x180027a1a  lea     r9, aMemoryAllocati; "Memory allocation error"
0x180027a21  mov     r8d, 274h
0x180027a27  jmp     short loc_180027A36
0x180027a29  lea     r9, aFailedToInitia_9; "Failed to initialize dll name."
0x180027a30  mov     r8d, 290h
0x180027a36  lea     rdx, aApphelpchecksh_0; "ApphelpCheckShellObject"
0x180027a3d  mov     ecx, edi
0x180027a3f  call    AslLogCallPrintf
0x180027a44  jmp     loc_18002793B
```
