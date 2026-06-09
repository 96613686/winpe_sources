# std::basic_filebuf<ushort,std::char_traits<ushort>>::_Endwrite(void)

- ea: `0x14000d50c`
- end: `0x14000d5e2`
- name: `?_Endwrite@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAA_NXZ`
- size: `214`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000bbb0`
- `0x14000bc90`
- `0x14000d5e4`

## callees

- `0x14000d50c`
- `0x1400137e0`
- `0x140014c70`

## import_xrefs

- `MSVCP140!?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x14000d56e`
- `MSVCP140!?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x14000d56e`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x14000d5ca`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x14000d5ca`

## pseudocode

```c
bool __fastcall std::basic_filebuf<unsigned short>::_Endwrite(__int64 a1)
{
  int v2; // eax
  int v3; // eax
  __int64 v5; // rdi
  _BYTE *v6; // [rsp+30h] [rbp-38h] BYREF
  _BYTE Buffer[32]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v8; // [rsp+58h] [rbp-10h] BYREF

  if ( !*(_QWORD *)(a1 + 104) || !*(_BYTE *)(a1 + 114) )
    return 1;
  if ( (*(unsigned __int16 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFF) == 0xFFFF )
    return 0;
  v2 = std::codecvt<unsigned short,char,_Mbstatet>::unshift(*(_QWORD *)(a1 + 104), a1 + 116, Buffer, &v8, &v6);
  if ( v2 )
  {
    v3 = v2 - 1;
    if ( v3 )
    {
      if ( v3 == 2 )
      {
        *(_BYTE *)(a1 + 114) = 0;
        return 1;
      }
      return 0;
    }
  }
  else
  {
    *(_BYTE *)(a1 + 114) = 0;
  }
  if ( v6 == Buffer )
    return *(_BYTE *)(a1 + 114) == 0;
  _mm_lfence();
  v5 = v6 - Buffer;
  if ( v5 == fwrite(Buffer, 1u, v6 - Buffer, *(FILE **)(a1 + 128)) )
    return *(_BYTE *)(a1 + 114) == 0;
  return 0;
}

```

## disassembly

```asm
0x14000d50c  mov     [rsp+arg_8], rbx
0x14000d511  push    rdi
0x14000d512  sub     rsp, 60h
0x14000d516  mov     rax, cs:__security_cookie
0x14000d51d  xor     rax, rsp
0x14000d520  mov     [rsp+68h+var_10], rax
0x14000d525  cmp     qword ptr [rcx+68h], 0
0x14000d52a  mov     rbx, rcx
0x14000d52d  jz      short loc_14000D586
0x14000d52f  cmp     byte ptr [rcx+72h], 0
0x14000d533  jz      short loc_14000D586
0x14000d535  mov     rax, [rcx]
0x14000d538  mov     edi, 0FFFFh
0x14000d53d  mov     edx, edi
0x14000d53f  mov     rax, [rax+18h]
0x14000d543  call    cs:__guard_dispatch_icall_fptr
0x14000d549  cmp     ax, di
0x14000d54c  jz      loc_14000D5DE
0x14000d552  mov     rcx, [rbx+68h]
0x14000d556  lea     rax, [rsp+68h+var_38]
0x14000d55b  lea     rdx, [rbx+74h]
0x14000d55f  mov     [rsp+68h+var_48], rax
0x14000d564  lea     r9, [rsp+68h+var_10]
0x14000d569  lea     r8, [rsp+68h+Buffer]
0x14000d56e  call    cs:__imp_?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<ushort,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x14000d574  test    eax, eax
0x14000d576  jz      short loc_14000D5A0
0x14000d578  sub     eax, 1
0x14000d57b  jz      short loc_14000D5A4
0x14000d57d  cmp     eax, 2
0x14000d580  jnz     short loc_14000D5DE
0x14000d582  mov     byte ptr [rbx+72h], 0
0x14000d586  mov     al, 1
0x14000d588  mov     rcx, [rsp+68h+var_10]
0x14000d58d  xor     rcx, rsp; StackCookie
0x14000d590  call    __security_check_cookie
0x14000d595  mov     rbx, [rsp+68h+arg_8]
0x14000d59a  add     rsp, 60h
0x14000d59e  pop     rdi
0x14000d59f  retn
0x14000d5a0  mov     byte ptr [rbx+72h], 0
0x14000d5a4  mov     rdi, [rsp+68h+var_38]
0x14000d5a9  lea     rax, [rsp+68h+Buffer]
0x14000d5ae  sub     rdi, rax
0x14000d5b1  jz      short loc_14000D5D5
0x14000d5b3  lfence
0x14000d5b6  mov     r9, [rbx+80h]; Stream
0x14000d5bd  lea     rcx, [rsp+68h+Buffer]; Buffer
0x14000d5c2  mov     r8, rdi; ElementCount
0x14000d5c5  mov     edx, 1; ElementSize
0x14000d5ca  call    cs:__imp_fwrite
0x14000d5d0  cmp     rdi, rax
0x14000d5d3  jnz     short loc_14000D5DE
0x14000d5d5  cmp     byte ptr [rbx+72h], 0
0x14000d5d9  setz    al
0x14000d5dc  jmp     short loc_14000D588
0x14000d5de  xor     al, al
0x14000d5e0  jmp     short loc_14000D588
```
