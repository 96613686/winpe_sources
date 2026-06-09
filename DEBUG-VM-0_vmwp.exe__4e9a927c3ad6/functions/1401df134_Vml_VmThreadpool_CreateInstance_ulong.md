# Vml::VmThreadpool::CreateInstance(ulong)

- ea: `0x1401df134`
- end: `0x1401df204`
- name: `?CreateInstance@VmThreadpool@Vml@@SAPEAV12@K@Z`
- size: `208`
- prototype: `struct Vml::VmThreadpool *__fastcall(DWORD cthrdMost)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1401e0ed4`
- `0x14027551c`

## callees

- `0x140021d00`
- `0x140042240`
- `0x140054af0`
- `0x140132cec`
- `0x1401335fc`
- `0x1401de5f0`
- `0x1401df134`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1401df149`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1401df149`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1401df1c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1401df1c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1401df167`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1401df167`

## string_xrefs

- `0x1401df1e2`: `Failed to allocate private threadpool!\n`

## pseudocode

```c
struct Vml::VmThreadpool *__fastcall Vml::VmThreadpool::CreateInstance(DWORD cthrdMost)
{
  __int64 v2; // rbx
  struct _TP_POOL *Threadpool; // rax
  struct _TP_POOL *v4; // rdi
  void *v5; // rbx
  __int64 v6; // rax
  struct _TP_POOL *v8; // [rsp+40h] [rbp+18h]

  v2 = 0;
  Threadpool = CreateThreadpool(0);
  v4 = Threadpool;
  v8 = Threadpool;
  if ( Threadpool )
  {
    SetThreadpoolThreadMaximum(Threadpool, cthrdMost);
    try
    {
      v5 = operator new(0xB8u);
      memset_0(v5, 0, 0xB8u);
      v6 = Vml::VmNewThreadpool::VmNewThreadpool((Vml::VmNewThreadpool *)v5, v4);
    }
    catch ( ... )
    {
      v2 = 0;
      v4 = v8;
      goto LABEL_5;
    }
    v2 = v6;
    if ( v6 )
    {
      Vml::VmSharableObject::IncrementUserCount((Vml::VmSharableObject *)(v6 + *(int *)(*(_QWORD *)(v6 + 8) + 4LL) + 8LL));
      return (struct Vml::VmThreadpool *)v2;
    }
LABEL_5:
    CloseThreadpool(v4);
  }
  if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
    VmlDebugTrace(0x4000, L"Failed to allocate private threadpool!\n");
  return (struct Vml::VmThreadpool *)v2;
}

```

## disassembly

```asm
0x1401df134  mov     [rsp+arg_0], rbx
0x1401df139  mov     [rsp+arg_18], rsi
0x1401df13e  push    rdi
0x1401df13f  sub     rsp, 20h
0x1401df143  mov     esi, ecx
0x1401df145  xor     ebx, ebx
0x1401df147  xor     ecx, ecx; reserved
0x1401df149  call    cs:__imp_CreateThreadpool
0x1401df150  nop     dword ptr [rax+rax+00h]
0x1401df155  mov     rdi, rax
0x1401df158  mov     [rsp+28h+arg_10], rax
0x1401df15d  test    rax, rax
0x1401df160  jz      short loc_1401DF1D2
0x1401df162  mov     edx, esi; cthrdMost
0x1401df164  mov     rcx, rax; ptpp
0x1401df167  call    cs:__imp_SetThreadpoolThreadMaximum
0x1401df16e  nop     dword ptr [rax+rax+00h]
0x1401df173  nop
0x1401df174  mov     esi, 0B8h
0x1401df179  mov     ecx, esi; Size
0x1401df17b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401df180  mov     rbx, rax
0x1401df183  mov     r8d, esi; Size
0x1401df186  xor     edx, edx; Val
0x1401df188  mov     rcx, rax; void *
0x1401df18b  call    memset_0
0x1401df190  mov     rdx, rdi; struct _TP_POOL *
0x1401df193  mov     rcx, rbx; this
0x1401df196  call    ??0VmNewThreadpool@Vml@@AEAA@PEAU_TP_POOL@@@Z; Vml::VmNewThreadpool::VmNewThreadpool(_TP_POOL *)
0x1401df19b  mov     rbx, rax
0x1401df19e  test    rbx, rbx
0x1401df1a1  jz      short loc_1401DF1C3
0x1401df1a3  mov     rax, [rax+8]
0x1401df1a7  movsxd  rcx, dword ptr [rax+4]
0x1401df1ab  add     rcx, 8
0x1401df1af  add     rcx, rbx; this
0x1401df1b2  call    ?IncrementUserCount@VmSharableObject@Vml@@AEAAKXZ; Vml::VmSharableObject::IncrementUserCount(void)
0x1401df1b7  jmp     short loc_1401DF1F0
0x1401df1b9  mov     rbx, [rsp+28h+arg_8]
0x1401df1be  mov     rdi, [rsp+28h+arg_10]
0x1401df1c3  mov     rcx, rdi; ptpp
0x1401df1c6  call    cs:__imp_CloseThreadpool
0x1401df1cd  nop     dword ptr [rax+rax+00h]
0x1401df1d2  mov     edi, 4000h
0x1401df1d7  mov     ecx, edi
0x1401df1d9  call    VmlIsDebugTraceEnabled
0x1401df1de  test    eax, eax
0x1401df1e0  jz      short loc_1401DF1F0
0x1401df1e2  lea     rdx, aFailedToAlloca_3; "Failed to allocate private threadpool!"...
0x1401df1e9  mov     ecx, edi
0x1401df1eb  call    VmlDebugTrace
0x1401df1f0  mov     rax, rbx
0x1401df1f3  mov     rbx, [rsp+28h+arg_0]
0x1401df1f8  mov     rsi, [rsp+28h+arg_18]
0x1401df1fd  add     rsp, 20h
0x1401df201  pop     rdi
0x1401df202  retn
```
