# CSMBHelperClass::GetErrorCode(void *,ulong &)

- ea: `0x18000551c`
- end: `0x18000568c`
- name: `?GetErrorCode@CSMBHelperClass@@AEAAJPEAXAEAK@Z`
- size: `368`
- prototype: `__int64 __fastcall(CSMBHelperClass *this, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800046ac`

## callees

- `0x180001230`
- `0x18000551c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000566f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000566f`
- `KERNEL32!GetLastError` at `0x18000557b`
- `KERNEL32!GetLastError` at `0x1800055ed`
- `KERNEL32!GetLastError` at `0x18000557b`
- `KERNEL32!GetLastError` at `0x1800055ed`
- `wevtapi!EvtNext` at `0x180005571`
- `wevtapi!EvtNext` at `0x180005571`
- `wevtapi!EvtCreateRenderContext` at `0x1800055b0`
- `wevtapi!EvtCreateRenderContext` at `0x1800055b0`
- `wevtapi!EvtRender` at `0x1800055e3`
- `wevtapi!EvtRender` at `0x18000562d`
- `wevtapi!EvtRender` at `0x1800055e3`
- `wevtapi!EvtRender` at `0x18000562d`
- `wevtapi!EvtClose` at `0x18000564b`
- `wevtapi!EvtClose` at `0x180005661`
- `wevtapi!EvtClose` at `0x18000564b`
- `wevtapi!EvtClose` at `0x180005661`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::GetErrorCode(CSMBHelperClass *this, void *a2, unsigned int *a3)
{
  unsigned int *v3; // rdi
  void *v5; // rsi
  signed int LastError; // eax
  unsigned int v7; // ebx
  EVT_HANDLE RenderContext; // rax
  DWORD PropertyCount; // [rsp+40h] [rbp-10h] BYREF
  HANDLE Events; // [rsp+48h] [rbp-8h] BYREF
  DWORD BufferSize; // [rsp+70h] [rbp+20h] BYREF
  int v13; // [rsp+74h] [rbp+24h]
  DWORD v14; // [rsp+88h] [rbp+38h] BYREF

  v13 = HIDWORD(this);
  v3 = 0;
  Events = 0;
  v14 = 0;
  BufferSize = 0;
  v5 = 0;
  PropertyCount = 0;
  if ( !EvtNext(a2, 1u, &Events, 0x3E8u, 0, &v14) )
    goto LABEL_2;
  if ( !v14 )
  {
    v7 = -2147467259;
    goto LABEL_12;
  }
  if ( (RenderContext = EvtCreateRenderContext(0, 0, 2u), (v5 = RenderContext) != 0)
    && (EvtRender(RenderContext, Events, 0, BufferSize, 0, &BufferSize, &PropertyCount) || GetLastError() == 122)
    && ((v3 = (unsigned int *)operator new[](BufferSize)) == 0
     || EvtRender(v5, Events, 0, BufferSize, v3, &BufferSize, &PropertyCount)) )
  {
    v7 = 0;
    *a3 = *v3;
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_12:
  if ( Events )
  {
    EvtClose(Events);
    Events = 0;
  }
  if ( v5 )
    EvtClose(v5);
  if ( v3 )
    operator delete[](v3);
  return v7;
}

```

## disassembly

```asm
0x18000551c  mov     r11, rsp
0x18000551f  mov     [r11+10h], rbx
0x180005523  mov     [r11+18h], rsi
0x180005527  mov     [r11+8], rcx
0x18000552b  push    rbp
0x18000552c  push    rdi
0x18000552d  push    r14
0x18000552f  mov     rbp, rsp
0x180005532  sub     rsp, 50h
0x180005536  xor     edi, edi
0x180005538  mov     [rbp+Events], 0
0x180005540  mov     rax, rdx
0x180005543  mov     [rbp+arg_18], 0
0x18000554a  lea     rcx, [rbp+arg_18]
0x18000554e  mov     [rbp+BufferSize], edi
0x180005551  mov     [r11-40h], rcx
0x180005555  mov     r14, r8
0x180005558  xor     esi, esi
0x18000555a  mov     [rbp+var_10], edi
0x18000555d  lea     edx, [rdi+1]; EventsSize
0x180005560  mov     [rsp+50h+Flags], esi; Flags
0x180005564  mov     r9d, 3E8h; Timeout
0x18000556a  lea     r8, [rbp+Events]; Events
0x18000556e  mov     rcx, rax; ResultSet
0x180005571  call    cs:__imp_EvtNext
0x180005577  test    eax, eax
0x180005579  jnz     short loc_180005599
0x18000557b  call    cs:__imp_GetLastError
0x180005581  mov     ebx, eax
0x180005583  test    eax, eax
0x180005585  jle     loc_180005642
0x18000558b  movzx   ebx, ax
0x18000558e  or      ebx, 80070000h
0x180005594  jmp     loc_180005642
0x180005599  cmp     [rbp+arg_18], esi
0x18000559c  jnz     short loc_1800055A8
0x18000559e  mov     ebx, 80004005h
0x1800055a3  jmp     loc_180005642
0x1800055a8  xor     edx, edx; ValuePaths
0x1800055aa  xor     ecx, ecx; ValuePathsCount
0x1800055ac  lea     r8d, [rdx+2]; Flags
0x1800055b0  call    cs:__imp_EvtCreateRenderContext
0x1800055b6  mov     rsi, rax
0x1800055b9  test    rax, rax
0x1800055bc  jz      short loc_18000557B
0x1800055be  mov     r9d, [rbp+BufferSize]; BufferSize
0x1800055c2  lea     rax, [rbp+var_10]
0x1800055c6  mov     rdx, [rbp+Events]; Fragment
0x1800055ca  xor     r8d, r8d; Flags
0x1800055cd  mov     [rsp+50h+PropertyCount], rax; PropertyCount
0x1800055d2  mov     rcx, rsi; Context
0x1800055d5  lea     rax, [rbp+BufferSize]
0x1800055d9  mov     [rsp+50h+BufferUsed], rax; BufferUsed
0x1800055de  mov     qword ptr [rsp+50h+Flags], rdi; Buffer
0x1800055e3  call    cs:__imp_EvtRender
0x1800055e9  test    eax, eax
0x1800055eb  jnz     short loc_1800055F8
0x1800055ed  call    cs:__imp_GetLastError
0x1800055f3  cmp     eax, 7Ah ; 'z'
0x1800055f6  jnz     short loc_18000557B
0x1800055f8  mov     ecx, [rbp+BufferSize]; unsigned __int64
0x1800055fb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180005600  mov     rdi, rax
0x180005603  test    rax, rax
0x180005606  jz      short loc_18000563B
0x180005608  mov     r9d, [rbp+BufferSize]; BufferSize
0x18000560c  lea     rax, [rbp+var_10]
0x180005610  mov     rdx, [rbp+Events]; Fragment
0x180005614  xor     r8d, r8d; Flags
0x180005617  mov     [rsp+50h+PropertyCount], rax; PropertyCount
0x18000561c  mov     rcx, rsi; Context
0x18000561f  lea     rax, [rbp+BufferSize]
0x180005623  mov     [rsp+50h+BufferUsed], rax; BufferUsed
0x180005628  mov     qword ptr [rsp+50h+Flags], rdi; Buffer
0x18000562d  call    cs:__imp_EvtRender
0x180005633  test    eax, eax
0x180005635  jz      loc_18000557B
0x18000563b  mov     eax, [rdi]
0x18000563d  xor     ebx, ebx
0x18000563f  mov     [r14], eax
0x180005642  mov     rcx, [rbp+Events]; Object
0x180005646  test    rcx, rcx
0x180005649  jz      short loc_180005659
0x18000564b  call    cs:__imp_EvtClose
0x180005651  mov     [rbp+Events], 0
0x180005659  test    rsi, rsi
0x18000565c  jz      short loc_180005667
0x18000565e  mov     rcx, rsi; Object
0x180005661  call    cs:__imp_EvtClose
0x180005667  test    rdi, rdi
0x18000566a  jz      short loc_180005675
0x18000566c  mov     rcx, rdi
0x18000566f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005675  lea     r11, [rsp+50h+var_s0]
0x18000567a  mov     eax, ebx
0x18000567c  mov     rbx, [r11+28h]
0x180005680  mov     rsi, [r11+30h]
0x180005684  mov     rsp, r11
0x180005687  pop     r14
0x180005689  pop     rdi
0x18000568a  pop     rbp
0x18000568b  retn
```
