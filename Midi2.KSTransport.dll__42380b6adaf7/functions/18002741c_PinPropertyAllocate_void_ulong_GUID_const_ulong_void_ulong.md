# PinPropertyAllocate(void *,ulong,_GUID const &,ulong,void * *,ulong *)

- ea: `0x18002741c`
- end: `0x180027598`
- name: `?PinPropertyAllocate@@YAJPEAXKAEBU_GUID@@KPEAPEAXPEAK@Z`
- size: `380`
- prototype: `__int64 __fastcall(void *, unsigned int, const struct _GUID *, unsigned int, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018a08`
- `0x180018af8`

## callees

- `0x180004434`
- `0x18000544c`
- `0x18000a814`
- `0x18002741c`
- `0x180027650`

## string_xrefs

- `0x1800274d7`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`
- `0x18002752c`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`

## pseudocode

```c
__int64 __fastcall PinPropertyAllocate(void *a1, int a2, const struct _GUID *a3, int a4, void **a5, unsigned int *a6)
{
  __int128 v6; // xmm0
  int v8; // ebx
  void *v9; // rbx
  __int64 v10; // rdx
  __int64 result; // rax
  int v12; // eax
  unsigned int v13; // edi
  unsigned int *v14; // rcx
  int v15; // [rsp+20h] [rbp-50h]
  int v16; // [rsp+20h] [rbp-50h]
  unsigned int v17; // [rsp+38h] [rbp-38h]
  unsigned int v18; // [rsp+38h] [rbp-38h]
  __int128 InBuffer; // [rsp+50h] [rbp-20h] BYREF
  int v20; // [rsp+60h] [rbp-10h]
  int v21; // [rsp+64h] [rbp-Ch]
  int v22; // [rsp+68h] [rbp-8h]
  int v23; // [rsp+6Ch] [rbp-4h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  DWORD lpNumberOfBytesTransferred; // [rsp+88h] [rbp+18h] BYREF

  v6 = (__int128)*a3;
  v20 = a4;
  v22 = a2;
  InBuffer = v6;
  lpNumberOfBytesTransferred = 0;
  v21 = 1;
  v23 = 0;
  v8 = SyncIoctl(a1, 0x2F0003u, &InBuffer, 0x20u, 0, 0, &lpNumberOfBytesTransferred, v17, 0);
  if ( v8 != -2147024662 )
  {
    if ( v8 >= 0 )
      return 2147549183LL;
    result = 2147942450LL;
    if ( v8 == -2147024846 )
      return result;
LABEL_13:
    v10 = 196;
    goto LABEL_5;
  }
  if ( !lpNumberOfBytesTransferred )
    goto LABEL_13;
  v9 = operator new[](lpNumberOfBytesTransferred, (const struct std::nothrow_t *)std::nothrow);
  if ( !v9 )
  {
    v8 = -2147024882;
    v10 = 177;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\midi2\\libs\\midikscommon\\midikscommon.cpp",
      (const char *)(unsigned int)v8,
      v15);
    return (unsigned int)v8;
  }
  v12 = SyncIoctl(a1, 0x2F0003u, &InBuffer, 0x20u, v9, lpNumberOfBytesTransferred, 0, v18, 0);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v14 = a6;
    *a5 = v9;
    if ( v14 )
      *v14 = lpNumberOfBytesTransferred;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"avcore\\midi2\\libs\\midikscommon\\midikscommon.cpp",
      (const char *)(unsigned int)v12,
      v16);
    operator delete(v9);
    return v13;
  }
}

```

## disassembly

```asm
0x18002741c  mov     r11, rsp
0x18002741f  mov     [r11+8], rbx
0x180027423  mov     [r11+18h], rdi
0x180027427  push    rbp
0x180027428  mov     rbp, rsp
0x18002742b  sub     rsp, 70h
0x18002742f  movups  xmm0, xmmword ptr [r8]
0x180027433  mov     qword ptr [r11-38h], 0
0x18002743b  lea     rax, [rbp+arg_8]
0x18002743f  mov     [r11-48h], rax
0x180027443  lea     r8, [rbp+InBuffer]; lpInBuffer
0x180027447  mov     [rbp+var_10], r9d
0x18002744b  mov     rdi, rcx
0x18002744e  mov     [rbp+var_8], edx
0x180027451  mov     r9d, 20h ; ' '; nInBufferSize
0x180027457  mov     qword ptr [rbp+InBuffer], 0
0x18002745f  mov     edx, 2F0003h; dwIoControlCode
0x180027464  mov     qword ptr [rbp+InBuffer+8], 0
0x18002746c  mov     [rsp+70h+var_48], 0; DWORD
0x180027474  movdqu  [rbp+InBuffer], xmm0
0x180027479  mov     qword ptr [r11-58h], 0
0x180027481  mov     [rbp+arg_8], 0
0x180027488  mov     [rbp+var_C], 1
0x18002748f  mov     [rbp+var_4], 0
0x180027496  call    ?SyncIoctl@@YAJPEAXK0K0KPEAKK0@Z; SyncIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *,ulong,void *)
0x18002749b  mov     ebx, eax
0x18002749d  cmp     eax, 800700EAh
0x1800274a2  jnz     loc_18002756A
0x1800274a8  mov     eax, [rbp+arg_8]
0x1800274ab  test    eax, eax
0x1800274ad  jz      loc_180027577
0x1800274b3  mov     ecx, eax; unsigned __int64
0x1800274b5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800274bc  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800274c1  mov     rbx, rax
0x1800274c4  test    rax, rax
0x1800274c7  jnz     short loc_1800274ED
0x1800274c9  mov     ebx, 8007000Eh
0x1800274ce  mov     edx, 0B1h; void *
0x1800274d3  mov     rcx, [rbp+8]; this
0x1800274d7  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x1800274de  mov     r9d, ebx; char *
0x1800274e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800274e6  mov     eax, ebx
0x1800274e8  jmp     loc_180027586
0x1800274ed  mov     eax, [rbp+arg_8]
0x1800274f0  lea     r8, [rbp+InBuffer]; lpInBuffer
0x1800274f4  mov     [rsp+70h+var_30], 0; void *
0x1800274fd  mov     r9d, 20h ; ' '; nInBufferSize
0x180027503  mov     [rsp+70h+lpNumberOfBytesTransferred], 0; lpNumberOfBytesTransferred
0x18002750c  mov     edx, 2F0003h; dwIoControlCode
0x180027511  mov     [rsp+70h+var_48], eax; DWORD
0x180027515  mov     rcx, rdi; hFile
0x180027518  mov     [rsp+70h+var_50], rbx; int
0x18002751d  call    ?SyncIoctl@@YAJPEAXK0K0KPEAKK0@Z; SyncIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *,ulong,void *)
0x180027522  mov     edi, eax
0x180027524  test    eax, eax
0x180027526  jns     short loc_180027551
0x180027528  mov     rcx, [rbp+8]; this
0x18002752c  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x180027533  mov     r9d, eax; char *
0x180027536  mov     edx, 0BAh; void *
0x18002753b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027540  mov     edx, 1
0x180027545  mov     rcx, rbx; Block
0x180027548  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002754d  mov     eax, edi
0x18002754f  jmp     short loc_180027586
0x180027551  mov     rax, [rbp+arg_20]
0x180027555  mov     rcx, [rbp+arg_28]
0x180027559  mov     [rax], rbx
0x18002755c  test    rcx, rcx
0x18002755f  jz      short loc_180027566
0x180027561  mov     eax, [rbp+arg_8]
0x180027564  mov     [rcx], eax
0x180027566  xor     eax, eax
0x180027568  jmp     short loc_180027586
0x18002756a  test    ebx, ebx
0x18002756c  jns     short loc_180027581
0x18002756e  mov     eax, 80070032h
0x180027573  cmp     ebx, eax
0x180027575  jz      short loc_180027586
0x180027577  mov     edx, 0C4h
0x18002757c  jmp     loc_1800274D3
0x180027581  mov     eax, 8000FFFFh
0x180027586  lea     r11, [rsp+70h+var_s0]
0x18002758b  mov     rbx, [r11+10h]
0x18002758f  mov     rdi, [r11+20h]
0x180027593  mov     rsp, r11
0x180027596  pop     rbp
0x180027597  retn
```
