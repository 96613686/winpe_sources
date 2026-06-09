# AiInitializeLib

- ea: `0x140038a54`
- end: `0x140038b2c`
- name: `AiInitializeLib`
- size: `216`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400380c4`

## callees

- `0x140006f40`
- `0x1400252dc`
- `0x1400253ac`
- `0x140038a54`
- `0x140038b34`

## import_xrefs

- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140038aae`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140038aae`

## pseudocode

```c
__int64 AiInitializeLib()
{
  __int64 v0; // rbx
  int v1; // edi
  __int64 v2; // rcx

  memset(&AiPerfStats, 0, 0xC0u);
  AppHashAlgInitialized = 1;
  *(_OWORD *)&AppHashAlgHandle = 0;
  v0 = 0;
  while ( 1 )
  {
    v1 = BCryptOpenAlgorithmProvider(&AppHashAlgHandle + v0, off_1400096A8[v0], 0, 0);
    if ( v1 < 0 )
      break;
    v0 = (unsigned int)(v0 + 1);
    if ( (unsigned int)v0 >= 2 )
    {
      v1 = AiInitializeCertStore();
      if ( v1 >= 0 )
      {
        HashTable = 0;
        AipAppxInMemoryCache = 0;
        AipAppxInMemoryCacheInitialized = 1;
        qword_140019430 = 0;
        AipAppxRegCache = 0;
        AipAppxRegCacheInitialized = 1;
        AiInitializeConfiguration(v2);
        return (unsigned int)v1;
      }
      break;
    }
  }
  AiFreeLib();
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140038a54  mov     [rsp+arg_0], rbx
0x140038a59  mov     [rsp+arg_8], rdi
0x140038a5e  push    r14
0x140038a60  sub     rsp, 20h
0x140038a64  xor     edx, edx; Val
0x140038a66  lea     rcx, AiPerfStats; void *
0x140038a6d  mov     r8d, 0C0h; Size
0x140038a73  call    memset
0x140038a78  xorps   xmm0, xmm0
0x140038a7b  mov     cs:AppHashAlgInitialized, 1
0x140038a85  movups  cs:AppHashAlgHandle, xmm0
0x140038a8c  xor     ebx, ebx
0x140038a8e  lea     r14, cs:140000000h
0x140038a95  mov     rdx, ds:rva off_1400096A8[r14+rbx*8]; pszAlgId
0x140038a9d  lea     rcx, rva AppHashAlgHandle[r14]
0x140038aa4  lea     rcx, [rcx+rbx*8]; phAlgorithm
0x140038aa8  xor     r9d, r9d; dwFlags
0x140038aab  xor     r8d, r8d; pszImplementation
0x140038aae  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140038ab5  nop     dword ptr [rax+rax+00h]
0x140038aba  mov     edi, eax
0x140038abc  test    eax, eax
0x140038abe  js      short loc_140038B13
0x140038ac0  inc     ebx
0x140038ac2  cmp     ebx, 2
0x140038ac5  jb      short loc_140038A95
0x140038ac7  call    AiInitializeCertStore
0x140038acc  mov     edi, eax
0x140038ace  test    eax, eax
0x140038ad0  js      short loc_140038B13
0x140038ad2  mov     cs:HashTable, 0
0x140038add  mov     cs:AipAppxInMemoryCache, 0
0x140038ae8  mov     cs:AipAppxInMemoryCacheInitialized, 1
0x140038aef  mov     cs:qword_140019430, 0
0x140038afa  mov     cs:AipAppxRegCache, 0
0x140038b05  mov     cs:AipAppxRegCacheInitialized, 1
0x140038b0c  call    AiInitializeConfiguration
0x140038b11  jmp     short loc_140038B18
0x140038b13  call    AiFreeLib
0x140038b18  mov     rbx, [rsp+28h+arg_0]
0x140038b1d  mov     eax, edi
0x140038b1f  mov     rdi, [rsp+28h+arg_8]
0x140038b24  add     rsp, 20h
0x140038b28  pop     r14
0x140038b2a  retn
```
