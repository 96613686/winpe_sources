# CProviderUtils::LogError(long,uint)

- ea: `0x180017ef8`
- end: `0x180017fdd`
- name: `?LogError@CProviderUtils@@SAXJI@Z`
- size: `229`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c1c0`
- `0x18000c310`
- `0x18000c55c`
- `0x18000c870`

## callees

- `0x180001ac0`
- `0x180009480`
- `0x18000b884`
- `0x1800166a0`
- `0x180017ef8`
- `0x180017fe4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017fb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017fb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017fa2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017fa2`

## pseudocode

```c
void __fastcall CProviderUtils::LogError(unsigned int a1, unsigned int a2)
{
  unsigned __int16 *v3; // rdi
  int v4; // edx
  int v5; // r8d
  int v6; // r9d
  unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  int v9; // ecx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v11; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int16 *v12; // [rsp+38h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int16 *v14; // [rsp+50h] [rbp-28h]
  int v15; // [rsp+58h] [rbp-20h]
  int v16; // [rsp+5Ch] [rbp-1Ch]

  v12 = 0;
  v11 = 0;
  STRAPI_LoadFromResource(a2, &v11);
  v3 = v11;
  STRAPI_Format(&v12, L"%s: hr=0x%X", v11, a1);
  if ( (Microsoft_Windows_Security_SPP_UX_GenuineCenter_LoggingEnableBits & 2) != 0 )
  {
    v7 = v12;
    if ( v12 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v12[v8] );
      v9 = 2 * v8 + 2;
    }
    else
    {
      v7 = L"NULL";
      v9 = 10;
    }
    v14 = v7;
    v15 = v9;
    v16 = 0;
    McGenEventWrite_EventWriteTransfer(v9, v4, v5, v6, &v13);
  }
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
}

```

## disassembly

```asm
0x180017ef8  mov     r11, rsp
0x180017efb  mov     [r11+18h], rbx
0x180017eff  mov     [r11+20h], rsi
0x180017f03  push    rdi
0x180017f04  sub     rsp, 70h
0x180017f08  mov     rax, cs:__security_cookie
0x180017f0f  xor     rax, rsp
0x180017f12  mov     [rsp+78h+var_18], rax
0x180017f17  mov     eax, edx
0x180017f19  mov     ebx, ecx
0x180017f1b  xor     esi, esi
0x180017f1d  lea     rdx, [r11-48h]; unsigned __int16 **
0x180017f21  mov     ecx, eax; unsigned int
0x180017f23  mov     [r11-40h], rsi
0x180017f27  mov     [r11-48h], rsi
0x180017f2b  call    ?STRAPI_LoadFromResource@@YAJIPEAPEAG@Z; STRAPI_LoadFromResource(uint,ushort * *)
0x180017f30  mov     rdi, [rsp+78h+var_48]
0x180017f35  lea     rdx, aSHr0xX; "%s: hr=0x%X"
0x180017f3c  mov     r8, rdi
0x180017f3f  lea     rcx, [rsp+78h+var_40]; unsigned __int16 **
0x180017f44  mov     r9d, ebx
0x180017f47  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x180017f4c  test    cs:Microsoft_Windows_Security_SPP_UX_GenuineCenter_LoggingEnableBits, 2
0x180017f53  jz      short loc_180017F9D
0x180017f55  mov     rax, [rsp+78h+var_40]
0x180017f5a  test    rax, rax
0x180017f5d  jz      short loc_180017F75
0x180017f5f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180017f63  inc     rcx
0x180017f66  cmp     [rax+rcx*2], si
0x180017f6a  jnz     short loc_180017F63
0x180017f6c  lea     ecx, ds:2[rcx*2]
0x180017f73  jmp     short loc_180017F81
0x180017f75  lea     rax, aNull; "NULL"
0x180017f7c  mov     ecx, 0Ah; int
0x180017f81  mov     [rsp+78h+var_28], rax
0x180017f86  lea     rax, [rsp+78h+var_38]
0x180017f8b  mov     [rsp+78h+var_58], rax; PEVENT_DATA_DESCRIPTOR
0x180017f90  mov     [rsp+78h+var_20], ecx
0x180017f94  mov     [rsp+78h+var_1C], esi
0x180017f98  call    McGenEventWrite_EventWriteTransfer
0x180017f9d  test    rdi, rdi
0x180017fa0  jz      short loc_180017FBE
0x180017fa2  call    cs:__imp_GetProcessHeap
0x180017fa8  lea     r8, [rdi-4]; lpMem
0x180017fac  xor     edx, edx; dwFlags
0x180017fae  mov     rcx, rax; hHeap
0x180017fb1  call    cs:__imp_HeapFree
0x180017fb7  xor     ecx, ecx
0x180017fb9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180017fbe  mov     rcx, [rsp+78h+var_18]
0x180017fc3  xor     rcx, rsp; StackCookie
0x180017fc6  call    __security_check_cookie
0x180017fcb  lea     r11, [rsp+78h+var_8]
0x180017fd0  mov     rbx, [r11+20h]
0x180017fd4  mov     rsi, [r11+28h]
0x180017fd8  mov     rsp, r11
0x180017fdb  pop     rdi
0x180017fdc  retn
```
