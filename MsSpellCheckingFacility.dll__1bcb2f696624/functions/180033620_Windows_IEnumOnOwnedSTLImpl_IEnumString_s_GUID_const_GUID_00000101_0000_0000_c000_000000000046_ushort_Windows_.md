# Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromWstringToLpolestr,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>::Next(ulong,ushort * *,ulong *)

- ea: `0x180033620`
- end: `0x18003372d`
- name: `?Next@?$IEnumOnOwnedSTLImpl@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromWstringToLpolestr@Windows@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Windows@@UEAAJKPEAPEAGPEAK@Z`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180033620`
- `0x1800337cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800336ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800336ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033695`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033695`

## pseudocode

```c
__int64 __fastcall Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromWstringToLpolestr,std::vector<std::wstring>>::Next(
        __int64 a1,
        unsigned int a2,
        void **a3,
        unsigned int *a4)
{
  void **v5; // rbp
  unsigned int v8; // esi
  void **v9; // r14
  int v10; // edi
  __int64 i; // rbx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rdi
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r8
  void *v16; // rcx

  v5 = a3;
  if ( a4 )
    *a4 = 0;
  v8 = 0;
  v9 = a3;
  v10 = 0;
  for ( i = *(_QWORD *)(a1 + 32); i != *(_QWORD *)(a1 + 16); i += 32 )
  {
    if ( v8 >= a2 )
      goto LABEL_20;
    *v9 = 0;
    v12 = *(_QWORD *)(i + 16) + 1LL;
    if ( v12 > 0xFFFFFFFF )
    {
      v10 = -2147024362;
      goto LABEL_18;
    }
    v13 = (unsigned int)v12;
    if ( 8 * (unsigned __int64)(unsigned int)v12 > 0xFFFFFFFF
      || (v14 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)(8 * v12)), (*v9 = v14) == 0) )
    {
      v10 = -2147024882;
      goto LABEL_18;
    }
    if ( *(_QWORD *)(i + 24) <= 7u )
      v15 = (const unsigned __int16 *)i;
    else
      v15 = *(const unsigned __int16 **)i;
    if ( !ocscpy_s(v14, v13, v15) )
    {
      v10 = -2147467259;
LABEL_18:
      while ( v5 < v9 )
      {
        v16 = *v5++;
        CoTaskMemFree(v16);
      }
      v8 = 0;
LABEL_20:
      if ( v10 < 0 )
        goto LABEL_25;
      break;
    }
    v10 = 0;
    ++v9;
    ++v8;
  }
  if ( a4 )
    *a4 = v8;
  if ( v8 < a2 )
  {
    *v9 = 0;
    v10 = 1;
  }
LABEL_25:
  *(_QWORD *)(a1 + 32) = i;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180033620  push    rbx
0x180033622  push    rbp
0x180033623  push    rsi
0x180033624  push    rdi
0x180033625  push    r12
0x180033627  push    r13
0x180033629  push    r14
0x18003362b  push    r15
0x18003362d  sub     rsp, 28h
0x180033631  mov     r15, r9
0x180033634  mov     rbp, r8
0x180033637  mov     r12d, edx
0x18003363a  mov     r13, rcx
0x18003363d  test    r9, r9
0x180033640  jz      short loc_180033649
0x180033642  mov     dword ptr [r9], 0
0x180033649  xor     esi, esi
0x18003364b  mov     r14, rbp
0x18003364e  xor     edi, edi
0x180033650  mov     rbx, [rcx+20h]
0x180033654  mov     ecx, 0FFFFFFFFh
0x180033659  cmp     rbx, [r13+10h]
0x18003365d  jz      loc_1800336FD
0x180033663  cmp     esi, r12d
0x180033666  jnb     loc_1800336F9
0x18003366c  mov     qword ptr [r14], 0
0x180033673  mov     rax, [rbx+10h]
0x180033677  inc     rax
0x18003367a  cmp     rax, rcx
0x18003367d  ja      short loc_1800336DD
0x18003367f  mov     edi, eax
0x180033681  lea     rax, ds:0[rdi*8]
0x180033689  cmp     rax, rcx
0x18003368c  ja      short loc_1800336D6
0x18003368e  lea     ecx, ds:0[rdi*8]; cb
0x180033695  call    cs:__imp_CoTaskMemAlloc
0x18003369b  mov     [r14], rax
0x18003369e  test    rax, rax
0x1800336a1  jz      short loc_1800336D6
0x1800336a3  cmp     qword ptr [rbx+18h], 7
0x1800336a8  jbe     short loc_1800336AF
0x1800336aa  mov     r8, [rbx]
0x1800336ad  jmp     short loc_1800336B2
0x1800336af  mov     r8, rbx; unsigned __int16 *
0x1800336b2  mov     rdx, rdi; unsigned __int64
0x1800336b5  mov     rcx, rax; unsigned __int16 *
0x1800336b8  call    ?ocscpy_s@@YA_NPEAG_KPEBG@Z; ocscpy_s(ushort *,unsigned __int64,ushort const *)
0x1800336bd  test    al, al
0x1800336bf  jz      short loc_1800336CF
0x1800336c1  xor     edi, edi
0x1800336c3  add     r14, 8
0x1800336c7  add     rbx, 20h ; ' '
0x1800336cb  inc     esi
0x1800336cd  jmp     short loc_180033654
0x1800336cf  mov     edi, 80004005h
0x1800336d4  jmp     short loc_1800336F2
0x1800336d6  mov     edi, 8007000Eh
0x1800336db  jmp     short loc_1800336F2
0x1800336dd  mov     edi, 80070216h
0x1800336e2  jmp     short loc_1800336F2
0x1800336e4  mov     rcx, [rbp+0]; pv
0x1800336e8  add     rbp, 8
0x1800336ec  call    cs:__imp_CoTaskMemFree
0x1800336f2  cmp     rbp, r14
0x1800336f5  jb      short loc_1800336E4
0x1800336f7  xor     esi, esi
0x1800336f9  test    edi, edi
0x1800336fb  js      short loc_180033716
0x1800336fd  test    r15, r15
0x180033700  jz      short loc_180033705
0x180033702  mov     [r15], esi
0x180033705  cmp     esi, r12d
0x180033708  jnb     short loc_180033716
0x18003370a  mov     qword ptr [r14], 0
0x180033711  mov     edi, 1
0x180033716  mov     [r13+20h], rbx
0x18003371a  mov     eax, edi
0x18003371c  add     rsp, 28h
0x180033720  pop     r15
0x180033722  pop     r14
0x180033724  pop     r13
0x180033726  pop     r12
0x180033728  pop     rdi
0x180033729  pop     rsi
0x18003372a  pop     rbp
0x18003372b  pop     rbx
0x18003372c  retn
```
