# std::basic_filebuf<char,std::char_traits<char>>::_Endwrite(void)

- ea: `0x140020af0`
- end: `0x140020bc7`
- name: `?_Endwrite@?$basic_filebuf@DU?$char_traits@D@std@@@std@@IEAA_NXZ`
- size: `215`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140020cd4`
- `0x140021110`
- `0x140021220`

## callees

- `0x140003e50`
- `0x140020af0`
- `0x14009b010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x140020b56`
- `msvcp_win!?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x140020b56`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140020baf`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140020baf`

## pseudocode

```c
bool __fastcall std::filebuf::_Endwrite(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // eax
  __int64 v6; // rdi
  _BYTE *v7; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v9; // [rsp+58h] [rbp-10h] BYREF

  if ( !*(_QWORD *)(a1 + 104) || !*(_BYTE *)(a1 + 113) )
    return 1;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFFFFFFLL) == -1 )
    return 0;
  v2 = *(_QWORD *)(a1 + 104);
  v7 = 0;
  v3 = std::codecvt<char,char,_Mbstatet>::unshift(v2, a1 + 116, v8, &v9, &v7);
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 == 2 )
      {
        *(_BYTE *)(a1 + 113) = 0;
        return 1;
      }
      return 0;
    }
  }
  else
  {
    *(_BYTE *)(a1 + 113) = 0;
  }
  if ( v7 == v8 )
    return *(_BYTE *)(a1 + 113) == 0;
  v6 = v7 - v8;
  if ( v6 == _o_fwrite(v8, 1, v7 - v8, *(_QWORD *)(a1 + 128)) )
    return *(_BYTE *)(a1 + 113) == 0;
  return 0;
}

```

## disassembly

```asm
0x140020af0  mov     [rsp+arg_8], rbx
0x140020af5  push    rdi
0x140020af6  sub     rsp, 60h
0x140020afa  mov     rax, cs:__security_cookie
0x140020b01  xor     rax, rsp
0x140020b04  mov     [rsp+68h+var_10], rax
0x140020b09  cmp     qword ptr [rcx+68h], 0
0x140020b0e  mov     rbx, rcx
0x140020b11  jz      short loc_140020B6E
0x140020b13  cmp     byte ptr [rcx+71h], 0
0x140020b17  jz      short loc_140020B6E
0x140020b19  mov     rax, [rcx]
0x140020b1c  or      edx, 0FFFFFFFFh
0x140020b1f  mov     rax, [rax+18h]
0x140020b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020b28  cmp     eax, 0FFFFFFFFh
0x140020b2b  jz      loc_140020BC3
0x140020b31  mov     rcx, [rbx+68h]
0x140020b35  lea     rax, [rsp+68h+var_38]
0x140020b3a  lea     rdx, [rbx+74h]
0x140020b3e  mov     [rsp+68h+var_48], rax
0x140020b43  lea     r9, [rsp+68h+var_10]
0x140020b48  mov     [rsp+68h+var_38], 0
0x140020b51  lea     r8, [rsp+68h+var_30]
0x140020b56  call    cs:__imp_?unshift@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x140020b5c  test    eax, eax
0x140020b5e  jz      short loc_140020B88
0x140020b60  sub     eax, 1
0x140020b63  jz      short loc_140020B8C
0x140020b65  cmp     eax, 2
0x140020b68  jnz     short loc_140020BC3
0x140020b6a  mov     byte ptr [rbx+71h], 0
0x140020b6e  mov     al, 1
0x140020b70  mov     rcx, [rsp+68h+var_10]
0x140020b75  xor     rcx, rsp; StackCookie
0x140020b78  call    __security_check_cookie
0x140020b7d  mov     rbx, [rsp+68h+arg_8]
0x140020b82  add     rsp, 60h
0x140020b86  pop     rdi
0x140020b87  retn
0x140020b88  mov     byte ptr [rbx+71h], 0
0x140020b8c  mov     rdi, [rsp+68h+var_38]
0x140020b91  lea     rax, [rsp+68h+var_30]
0x140020b96  sub     rdi, rax
0x140020b99  jz      short loc_140020BBA
0x140020b9b  mov     r9, [rbx+80h]
0x140020ba2  lea     rcx, [rsp+68h+var_30]
0x140020ba7  mov     r8, rdi
0x140020baa  mov     edx, 1
0x140020baf  call    cs:__imp__o_fwrite
0x140020bb5  cmp     rdi, rax
0x140020bb8  jnz     short loc_140020BC3
0x140020bba  cmp     byte ptr [rbx+71h], 0
0x140020bbe  setz    al
0x140020bc1  jmp     short loc_140020B70
0x140020bc3  xor     al, al
0x140020bc5  jmp     short loc_140020B70
```
