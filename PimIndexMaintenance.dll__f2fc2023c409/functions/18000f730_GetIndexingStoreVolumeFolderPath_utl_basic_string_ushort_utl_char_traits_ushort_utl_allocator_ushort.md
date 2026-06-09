# GetIndexingStoreVolumeFolderPath(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x18000f730`
- end: `0x18000f7d9`
- name: `?GetIndexingStoreVolumeFolderPath@@YAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ee40`
- `0x18000f7e0`

## callees

- `0x18000f730`
- `0x1800104b8`
- `0x180012640`
- `0x180021240`

## import_xrefs

- `unistore!GetUSDeviceStoreFolderPath` at `0x18000f761`
- `unistore!GetUSDeviceStoreFolderPath` at `0x18000f761`

## pseudocode

```c
__int64 __fastcall GetIndexingStoreVolumeFolderPath(__int64 a1)
{
  int USDeviceStoreFolderPath; // ebx
  __int64 v3; // r8
  __int64 v4; // rdx
  __int64 v5; // r9
  __int64 v7; // r8
  unsigned __int16 v8[264]; // [rsp+30h] [rbp-228h] BYREF

  USDeviceStoreFolderPath = GetUSDeviceStoreFolderPath(v8, 0x104u);
  if ( USDeviceStoreFolderPath < 0 )
  {
    v4 = 1;
    v5 = 45;
LABEL_3:
    Log_HREvent_2((unsigned int)USDeviceStoreFolderPath, v4, v3, v5);
    return (unsigned int)USDeviceStoreFolderPath;
  }
  v7 = -1;
  do
    ++v7;
  while ( v8[v7] );
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           a1,
                           v8) )
  {
    v4 = 0;
    USDeviceStoreFolderPath = -2147024882;
    v5 = 47;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000f730  mov     [rsp+arg_8], rbx
0x18000f735  mov     [rsp+arg_10], rsi
0x18000f73a  push    rdi
0x18000f73b  sub     rsp, 250h
0x18000f742  mov     rax, cs:__security_cookie
0x18000f749  xor     rax, rsp
0x18000f74c  mov     [rsp+258h+var_18], rax
0x18000f754  mov     rdi, rcx
0x18000f757  mov     edx, 104h
0x18000f75c  lea     rcx, [rsp+258h+var_228]
0x18000f761  call    cs:__imp_?GetUSDeviceStoreFolderPath@@YAJPEAG_K@Z; GetUSDeviceStoreFolderPath(ushort *,unsigned __int64)
0x18000f767  xor     esi, esi
0x18000f769  mov     ebx, eax
0x18000f76b  test    eax, eax
0x18000f76d  jns     short loc_18000F781
0x18000f76f  lea     edx, [rsi+1]
0x18000f772  lea     r9d, [rsi+2Dh]
0x18000f776  mov     ecx, ebx
0x18000f778  call    Log_HREvent_2
0x18000f77d  mov     eax, ebx
0x18000f77f  jmp     short loc_18000F7B4
0x18000f781  lea     rax, [rsp+258h+var_228]
0x18000f786  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f78a  inc     r8
0x18000f78d  cmp     [rax+r8*2], si
0x18000f792  jnz     short loc_18000F78A
0x18000f794  lea     rdx, [rsp+258h+var_228]
0x18000f799  mov     rcx, rdi
0x18000f79c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000f7a1  test    al, al
0x18000f7a3  jnz     short loc_18000F7B2
0x18000f7a5  xor     edx, edx
0x18000f7a7  mov     ebx, 8007000Eh
0x18000f7ac  lea     r9d, [rdx+2Fh]
0x18000f7b0  jmp     short loc_18000F776
0x18000f7b2  xor     eax, eax
0x18000f7b4  mov     rcx, [rsp+258h+var_18]
0x18000f7bc  xor     rcx, rsp; StackCookie
0x18000f7bf  call    __security_check_cookie
0x18000f7c4  lea     r11, [rsp+258h+var_8]
0x18000f7cc  mov     rbx, [r11+18h]
0x18000f7d0  mov     rsi, [r11+20h]
0x18000f7d4  mov     rsp, r11
0x18000f7d7  pop     rdi
0x18000f7d8  retn
```
