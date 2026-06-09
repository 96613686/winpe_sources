# SetRegistry(ushort const *,_SECURITY_ATTRIBUTES *,ATL::CRegKey &)

- ea: `0x1400074b8`
- end: `0x1400075ef`
- name: `?SetRegistry@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@AEAVCRegKey@ATL@@@Z`
- size: `311`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _SECURITY_ATTRIBUTES *, HKEY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000735c`
- `0x1400073fc`

## callees

- `0x140006aa4`
- `0x1400074b8`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1400074f9`
- `msvcrt!wcsrchr` at `0x1400074f9`
- `msvcrt!memcpy` at `0x14000754f`
- `msvcrt!memcpy` at `0x14000754f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400075ac`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400075ac`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140007530`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140007530`

## pseudocode

```c
__int64 __fastcall SetRegistry(const unsigned __int16 *a1, struct _SECURITY_ATTRIBUTES *a2, HKEY *a3)
{
  HKEY *v3; // r13
  int v4; // edi
  wchar_t *v5; // rax
  __int64 v6; // rbx
  int v7; // r15d
  unsigned __int64 v8; // rax
  unsigned __int16 *v9; // rax
  HKEY v10; // rdx
  unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // r14
  size_t v13; // rbx
  bool v14; // cc
  __int64 v16; // [rsp+0h] [rbp-88h] BYREF
  unsigned int v17; // [rsp+20h] [rbp-68h]
  unsigned int v18; // [rsp+28h] [rbp-60h]
  unsigned __int16 *v19; // [rsp+40h] [rbp-48h]
  int v20; // [rsp+90h] [rbp+8h]

  v3 = a3;
  v4 = -2147467259;
  v19 = 0;
  v5 = wcsrchr(L"SOFTWARE\\Microsoft\\WBEM\\PROVIDERS\\Performance", 0x5Cu);
  if ( v5 )
  {
    v6 = v5 - L"SOFTWARE\\Microsoft\\WBEM\\PROVIDERS\\Performance";
    v7 = 0;
    v20 = 0;
    v8 = 2 * (v6 + 1);
    if ( !is_mul_ok(v6 + 1, 2u) )
      v8 = -1;
    try
    {
      v9 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(v8);
      v12 = v9;
      v19 = v9;
      if ( v9 )
      {
        v13 = v6;
        memcpy(v9, L"SOFTWARE\\Microsoft\\WBEM\\PROVIDERS\\Performance", v13 * 2);
        v12[v13] = 0;
        v7 = 1;
        v20 = 1;
      }
    }
    catch ( ... )
    {
      v10 = (HKEY)&v16;
      v3 = a3;
      v4 = -2147467259;
      v12 = v19;
      v7 = v20;
    }
    if ( v7 )
      v4 = ATL::CRegKey::Create(v3, v10, v12, v11, v17, v18, 0);
    if ( v12 )
      CWin32DefaultArena::WbemMemFree(v12);
    v14 = v4 <= 0;
    if ( !v4 )
    {
      v4 = ATL::CRegKey::Create(v3, v10, L"SOFTWARE\\Microsoft\\WBEM\\PROVIDERS\\Performance", v11, v17, v18, a2);
      v14 = v4 <= 0;
    }
    if ( !v14 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400074b8  mov     [rsp+arg_10], r8
0x1400074bd  mov     [rsp+arg_8], rdx
0x1400074c2  mov     [rsp+arg_0], rcx
0x1400074c7  push    rbx
0x1400074c8  push    rsi
0x1400074c9  push    rdi
0x1400074ca  push    r12
0x1400074cc  push    r13
0x1400074ce  push    r14
0x1400074d0  push    r15
0x1400074d2  sub     rsp, 50h
0x1400074d6  mov     r13, r8
0x1400074d9  mov     edi, 80004005h
0x1400074de  mov     [rsp+88h+arg_18], edi
0x1400074e5  xor     esi, esi
0x1400074e7  mov     [rsp+88h+var_48], rsi
0x1400074ec  lea     edx, [rsi+5Ch]; Ch
0x1400074ef  lea     r12, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\WBEM\\PROVIDERS\\P"...
0x1400074f6  mov     rcx, r12; Str
0x1400074f9  call    cs:__imp_wcsrchr
0x1400074ff  mov     rbx, rax
0x140007502  test    rax, rax
0x140007505  jz      loc_1400075DD
0x14000750b  sub     rbx, r12
0x14000750e  sar     rbx, 1
0x140007511  mov     r15d, esi
0x140007514  mov     dword ptr [rsp+88h+arg_0], esi
0x14000751b  lea     rcx, [rbx+1]
0x14000751f  lea     eax, [rsi+2]
0x140007522  mul     rcx
0x140007525  lea     rcx, [rsi-1]
0x140007529  cmovb   rax, rcx
0x14000752d  mov     rcx, rax
0x140007530  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140007536  mov     r14, rax
0x140007539  mov     [rsp+88h+var_48], rax
0x14000753e  test    rax, rax
0x140007541  jz      short loc_140007566
0x140007543  add     rbx, rbx
0x140007546  mov     r8, rbx; Size
0x140007549  mov     rdx, r12; Src
0x14000754c  mov     rcx, rax; void *
0x14000754f  call    cs:__imp_memcpy
0x140007555  mov     [rbx+r14], si
0x14000755a  lea     r15d, [rsi+1]
0x14000755e  mov     dword ptr [rsp+88h+arg_0], r15d
0x140007566  jmp     short loc_14000758D
0x140007568  xor     esi, esi
0x14000756a  lea     r12, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\WBEM\\PROVIDERS\\P"...
0x140007571  mov     r13, [rsp+88h+arg_10]
0x140007579  mov     edi, [rsp+88h+arg_18]
0x140007580  mov     r14, [rsp+88h+var_48]
0x140007585  mov     r15d, dword ptr [rsp+88h+arg_0]
0x14000758d  test    r15d, r15d
0x140007590  jz      short loc_1400075A4
0x140007592  mov     [rsp+88h+var_58], rsi; struct _SECURITY_ATTRIBUTES *
0x140007597  mov     r8, r14; unsigned __int16 *
0x14000759a  mov     rcx, r13; this
0x14000759d  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1400075a2  mov     edi, eax
0x1400075a4  test    r14, r14
0x1400075a7  jz      short loc_1400075B2
0x1400075a9  mov     rcx, r14
0x1400075ac  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1400075b2  test    edi, edi
0x1400075b4  jnz     short loc_1400075D2
0x1400075b6  mov     rax, [rsp+88h+arg_8]
0x1400075be  mov     [rsp+88h+var_58], rax; struct _SECURITY_ATTRIBUTES *
0x1400075c3  mov     r8, r12; unsigned __int16 *
0x1400075c6  mov     rcx, r13; this
0x1400075c9  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1400075ce  mov     edi, eax
0x1400075d0  test    eax, eax
0x1400075d2  jle     short loc_1400075DD
0x1400075d4  movzx   edi, di
0x1400075d7  or      edi, 80070000h
0x1400075dd  mov     eax, edi
0x1400075df  add     rsp, 50h
0x1400075e3  pop     r15
0x1400075e5  pop     r14
0x1400075e7  pop     r13
0x1400075e9  pop     r12
0x1400075eb  pop     rdi
0x1400075ec  pop     rsi
0x1400075ed  pop     rbx
0x1400075ee  retn
```
