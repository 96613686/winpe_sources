# FaxGetServicePrintersW

- ea: `0x18000fee0`
- end: `0x180010292`
- name: `FaxGetServicePrintersW`
- size: `946`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000fd80`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000fee0`
- `0x18002bb58`
- `0x18003466c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001001d`
- `RPCRT4!NdrClientCall3` at `0x18001001d`
- `KERNEL32!SetLastError` at `0x18000ff59`
- `KERNEL32!SetLastError` at `0x18000ffa0`
- `KERNEL32!SetLastError` at `0x180010099`
- `KERNEL32!SetLastError` at `0x18001010b`
- `KERNEL32!SetLastError` at `0x180010247`
- `KERNEL32!SetLastError` at `0x18000ff59`
- `KERNEL32!SetLastError` at `0x18000ffa0`
- `KERNEL32!SetLastError` at `0x180010099`
- `KERNEL32!SetLastError` at `0x18001010b`
- `KERNEL32!SetLastError` at `0x180010247`

## pseudocode

```c
__int64 __fastcall FaxGetServicePrintersW(__int64 a1, LPVOID *a2, _DWORD *a3)
{
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rax
  CLIENT_CALL_RETURN v9; // rax
  _QWORD *v10; // rdx
  unsigned int v11; // r10d
  unsigned int v12; // r9d
  unsigned __int64 v13; // rcx
  _WORD *v14; // rcx
  unsigned int v15; // eax
  unsigned __int64 v16; // rcx
  _WORD *v17; // rcx
  unsigned int v18; // eax
  unsigned __int64 v19; // rcx
  _WORD *v20; // rcx
  unsigned int v21; // eax
  unsigned int v23; // [rsp+80h] [rbp+8h] BYREF
  LPVOID *v24; // [rsp+88h] [rbp+10h]
  _DWORD *v25; // [rsp+90h] [rbp+18h]
  CLIENT_CALL_RETURN v26; // [rsp+98h] [rbp+20h]

  v25 = a3;
  v24 = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 324, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
  }
  if ( !a1 || !*(_DWORD *)a1 || *(_DWORD *)(a1 + 16) )
  {
    SetLastError(6u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v7 = 325;
LABEL_55:
    WPP_SF_(v6[2], v7, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
  }
  if ( !a2 )
  {
    SetLastError(0x57u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v7 = 326;
    goto LABEL_55;
  }
  if ( !a3 )
  {
    SetLastError(0x57u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v7 = 327;
    goto LABEL_55;
  }
  v23 = 0;
  *a2 = 0;
  *a3 = 0;
  v8 = *(_QWORD **)(a1 + 32);
  v26.Simple = 0;
  v9.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, *v8, a2, &v23, a3).Pointer;
  v26.Pointer = v9.Pointer;
  if ( LODWORD(v9.Pointer) )
  {
    SetLastError((DWORD)v9.Pointer);
  }
  else if ( (unsigned int)MarshallUpStructuresArray(a2, &v23, (unsigned int)*a3, &fax_printer_info_fields, 24, 0) )
  {
    v10 = *a2;
    v11 = 0;
    if ( !*a3 )
      return 1;
    v12 = v23;
    while ( 1 )
    {
      v13 = v10[3 * v11];
      if ( v13 > v12 )
        break;
      if ( v13 )
      {
        v14 = (char *)*a2 + v13;
        v10[3 * v11] = v14;
        v12 = v23;
        if ( v14 )
        {
          v15 = (v23 + *(_DWORD *)a2 - (_DWORD)v14) >> 1;
          if ( !v15 )
            return 0;
          while ( *v14 )
          {
            if ( !--v15 )
              return 0;
            ++v14;
          }
        }
      }
      v16 = v10[3 * v11 + 2];
      if ( v16 > v12 )
        break;
      if ( v16 )
      {
        v17 = (char *)*a2 + v16;
        v10[3 * v11 + 2] = v17;
        v12 = v23;
        if ( v17 )
        {
          v18 = (v23 + *(_DWORD *)a2 - (_DWORD)v17) >> 1;
          if ( !v18 )
            return 0;
          while ( *v17 )
          {
            if ( !--v18 )
              return 0;
            ++v17;
          }
        }
      }
      v19 = v10[3 * v11 + 1];
      if ( v19 > v12 )
        break;
      if ( v19 )
      {
        v20 = (char *)*a2 + v19;
        v10[3 * v11 + 1] = v20;
        v12 = v23;
        if ( v20 )
        {
          v21 = (v23 + *(_DWORD *)a2 - (_DWORD)v20) >> 1;
          if ( !v21 )
            return 0;
          while ( *v20 )
          {
            if ( !--v21 )
              return 0;
            ++v20;
          }
        }
      }
      if ( ++v11 >= *a3 )
        return 1;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 329, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    }
    SetLastError(0x54Fu);
    pMemFree(*a2);
    *a2 = 0;
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000fee0  mov     [rsp+arg_10], r8
0x18000fee5  mov     [rsp+arg_8], rdx
0x18000feea  push    rbx
0x18000feeb  push    rsi
0x18000feec  push    rdi
0x18000feed  push    r12
0x18000feef  push    r15
0x18000fef1  sub     rsp, 50h
0x18000fef5  mov     r12, r8
0x18000fef8  mov     rsi, rdx
0x18000fefb  mov     rbx, rcx
0x18000fefe  lea     r15, WPP_GLOBAL_Control
0x18000ff05  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff0c  cmp     rcx, r15
0x18000ff0f  jz      short loc_18000FF35
0x18000ff11  test    dword ptr [rcx+1Ch], 1000h
0x18000ff18  jz      short loc_18000FF35
0x18000ff1a  cmp     byte ptr [rcx+19h], 5
0x18000ff1e  jb      short loc_18000FF35
0x18000ff20  mov     edx, 144h
0x18000ff25  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000ff2c  mov     rcx, [rcx+10h]
0x18000ff30  call    WPP_SF_
0x18000ff35  xor     edi, edi
0x18000ff37  test    rbx, rbx
0x18000ff3a  jz      loc_180010242
0x18000ff40  cmp     [rbx], edi
0x18000ff42  jz      loc_180010242
0x18000ff48  cmp     [rbx+10h], edi
0x18000ff4b  jnz     loc_180010242
0x18000ff51  test    rsi, rsi
0x18000ff54  jnz     short loc_18000FF96
0x18000ff56  lea     ecx, [rdi+57h]; dwErrCode
0x18000ff59  call    cs:__imp_SetLastError
0x18000ff60  nop     dword ptr [rax+rax+00h]
0x18000ff65  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff6c  cmp     rcx, r15
0x18000ff6f  jz      loc_180010283
0x18000ff75  test    dword ptr [rcx+1Ch], 1000h
0x18000ff7c  jz      loc_180010283
0x18000ff82  cmp     byte ptr [rcx+19h], 2
0x18000ff86  jb      loc_180010283
0x18000ff8c  mov     edx, 146h
0x18000ff91  jmp     loc_180010273
0x18000ff96  test    r12, r12
0x18000ff99  jnz     short loc_18000FFDD
0x18000ff9b  lea     ecx, [r12+57h]; dwErrCode
0x18000ffa0  call    cs:__imp_SetLastError
0x18000ffa7  nop     dword ptr [rax+rax+00h]
0x18000ffac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffb3  cmp     rcx, r15
0x18000ffb6  jz      loc_180010283
0x18000ffbc  test    dword ptr [rcx+1Ch], 1000h
0x18000ffc3  jz      loc_180010283
0x18000ffc9  cmp     byte ptr [rcx+19h], 2
0x18000ffcd  jb      loc_180010283
0x18000ffd3  mov     edx, 147h
0x18000ffd8  jmp     loc_180010273
0x18000ffdd  mov     [rsp+78h+arg_0], edi
0x18000ffe4  mov     [rsi], rdi
0x18000ffe7  mov     [r12], edi
0x18000ffeb  mov     rax, [rbx+20h]
0x18000ffef  mov     [rsp+78h+arg_18], rdi
0x18000fff7  mov     [rsp+78h+var_48], r12
0x18000fffc  lea     rcx, [rsp+78h+arg_0]
0x180010004  mov     [rsp+78h+var_50], rcx
0x180010009  mov     [rsp+78h+var_58], rsi
0x18001000e  mov     r9, [rax]
0x180010011  xor     r8d, r8d; pReturnValue
0x180010014  xor     edx, edx; nProcNum
0x180010016  lea     rcx, pProxyInfo; pProxyInfo
0x18001001d  call    cs:__imp_NdrClientCall3
0x180010024  nop     dword ptr [rax+rax+00h]
0x180010029  mov     rbx, rax
0x18001002c  mov     [rsp+78h+arg_18], rax
0x180010034  mov     [rsp+78h+var_38], eax
0x180010038  jmp     short loc_180010093
0x18001003a  mov     ebx, eax
0x18001003c  mov     [rsp+78h+var_38], eax
0x180010040  lea     rdx, WPP_GLOBAL_Control
0x180010047  mov     rcx, cs:WPP_GLOBAL_Control
0x18001004e  cmp     rcx, rdx
0x180010051  jz      short loc_18001007A
0x180010053  test    dword ptr [rcx+1Ch], 1000h
0x18001005a  jz      short loc_18001007A
0x18001005c  cmp     byte ptr [rcx+19h], 2
0x180010060  jb      short loc_18001007A
0x180010062  mov     edx, 148h
0x180010067  mov     r9d, eax
0x18001006a  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x180010071  mov     rcx, [rcx+10h]
0x180010075  call    WPP_SF_d
0x18001007a  lea     r15, WPP_GLOBAL_Control
0x180010081  xor     edi, edi
0x180010083  mov     r12, [rsp+78h+arg_10]
0x18001008b  mov     rsi, [rsp+78h+arg_8]
0x180010093  test    ebx, ebx
0x180010095  jz      short loc_1800100AA
0x180010097  mov     ecx, ebx; dwErrCode
0x180010099  call    cs:__imp_SetLastError
0x1800100a0  nop     dword ptr [rax+rax+00h]
0x1800100a5  jmp     loc_180010283
0x1800100aa  mov     dword ptr [rsp+78h+var_50], edi
0x1800100ae  mov     [rsp+78h+var_58], 18h
0x1800100b7  lea     r9, ?fax_printer_info_fields@@3PAU_FieldInfo@@A; _FieldInfo near * fax_printer_info_fields
0x1800100be  mov     r8d, [r12]
0x1800100c2  lea     rdx, [rsp+78h+arg_0]
0x1800100ca  mov     rcx, rsi
0x1800100cd  call    MarshallUpStructuresArray
0x1800100d2  test    eax, eax
0x1800100d4  jnz     short loc_18001012B
0x1800100d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800100dd  cmp     rcx, r15
0x1800100e0  jz      short loc_180010106
0x1800100e2  test    dword ptr [rcx+1Ch], 1000h
0x1800100e9  jz      short loc_180010106
0x1800100eb  cmp     byte ptr [rcx+19h], 2
0x1800100ef  jb      short loc_180010106
0x1800100f1  mov     edx, 149h
0x1800100f6  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x1800100fd  mov     rcx, [rcx+10h]
0x180010101  call    WPP_SF_
0x180010106  mov     ecx, 54Fh; dwErrCode
0x18001010b  call    cs:__imp_SetLastError
0x180010112  nop     dword ptr [rax+rax+00h]
0x180010117  mov     rcx, [rsi]; lpMem
0x18001011a  call    pMemFree
0x18001011f  mov     [rsi], rdi
0x180010122  mov     [r12], edi
0x180010126  jmp     loc_180010283
0x18001012b  mov     rdx, [rsi]
0x18001012e  mov     r10d, edi
0x180010131  cmp     [r12], edi
0x180010135  jbe     loc_18001023B
0x18001013b  or      r11d, 0FFFFFFFFh
0x18001013f  mov     r9d, [rsp+78h+arg_0]
0x180010147  mov     eax, r10d
0x18001014a  lea     r8, [rax+rax*2]
0x18001014e  mov     rcx, [rdx+r8*8]
0x180010152  mov     eax, r9d
0x180010155  cmp     rcx, rax
0x180010158  ja      loc_180010283
0x18001015e  test    rcx, rcx
0x180010161  jz      short loc_18001019A
0x180010163  add     rcx, [rsi]
0x180010166  mov     [rdx+r8*8], rcx
0x18001016a  mov     r9d, [rsp+78h+arg_0]
0x180010172  test    rcx, rcx
0x180010175  jz      short loc_18001019A
0x180010177  mov     eax, [rsi]
0x180010179  sub     eax, ecx
0x18001017b  add     eax, r9d
0x18001017e  shr     eax, 1
0x180010180  jz      loc_180010283
0x180010186  cmp     di, [rcx]
0x180010189  jz      short loc_18001019A
0x18001018b  add     eax, r11d
0x18001018e  jz      loc_180010283
0x180010194  add     rcx, 2
0x180010198  jmp     short loc_180010186
0x18001019a  mov     rcx, [rdx+r8*8+10h]
0x18001019f  mov     eax, r9d
0x1800101a2  cmp     rcx, rax
0x1800101a5  ja      loc_180010283
0x1800101ab  test    rcx, rcx
0x1800101ae  jz      short loc_1800101E8
0x1800101b0  add     rcx, [rsi]
0x1800101b3  mov     [rdx+r8*8+10h], rcx
0x1800101b8  mov     r9d, [rsp+78h+arg_0]
0x1800101c0  test    rcx, rcx
0x1800101c3  jz      short loc_1800101E8
0x1800101c5  mov     eax, [rsi]
0x1800101c7  sub     eax, ecx
0x1800101c9  add     eax, r9d
0x1800101cc  shr     eax, 1
0x1800101ce  jz      loc_180010283
0x1800101d4  cmp     di, [rcx]
0x1800101d7  jz      short loc_1800101E8
0x1800101d9  add     eax, r11d
0x1800101dc  jz      loc_180010283
0x1800101e2  add     rcx, 2
0x1800101e6  jmp     short loc_1800101D4
0x1800101e8  mov     rcx, [rdx+r8*8+8]
0x1800101ed  mov     eax, r9d
0x1800101f0  cmp     rcx, rax
0x1800101f3  ja      loc_180010283
0x1800101f9  test    rcx, rcx
0x1800101fc  jz      short loc_18001022E
0x1800101fe  add     rcx, [rsi]
0x180010201  mov     [rdx+r8*8+8], rcx
0x180010206  mov     r9d, [rsp+78h+arg_0]
0x18001020e  test    rcx, rcx
0x180010211  jz      short loc_18001022E
0x180010213  mov     eax, [rsi]
0x180010215  sub     eax, ecx
0x180010217  add     eax, r9d
0x18001021a  shr     eax, 1
0x18001021c  jz      short loc_180010283
0x18001021e  cmp     di, [rcx]
0x180010221  jz      short loc_18001022E
0x180010223  add     eax, r11d
0x180010226  jz      short loc_180010283
0x180010228  add     rcx, 2
0x18001022c  jmp     short loc_18001021E
0x18001022e  inc     r10d
0x180010231  cmp     r10d, [r12]
0x180010235  jb      loc_180010147
0x18001023b  mov     eax, 1
0x180010240  jmp     short loc_180010285
0x180010242  mov     ecx, 6; dwErrCode
0x180010247  call    cs:__imp_SetLastError
0x18001024e  nop     dword ptr [rax+rax+00h]
0x180010253  mov     rcx, cs:WPP_GLOBAL_Control
0x18001025a  cmp     rcx, r15
0x18001025d  jz      short loc_180010283
0x18001025f  test    dword ptr [rcx+1Ch], 1000h
0x180010266  jz      short loc_180010283
0x180010268  cmp     byte ptr [rcx+19h], 2
0x18001026c  jb      short loc_180010283
0x18001026e  mov     edx, 145h
0x180010273  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18001027a  mov     rcx, [rcx+10h]
0x18001027e  call    WPP_SF_
0x180010283  xor     eax, eax
0x180010285  add     rsp, 50h
0x180010289  pop     r15
0x18001028b  pop     r12
0x18001028d  pop     rdi
0x18001028e  pop     rsi
0x18001028f  pop     rbx
0x180010290  retn
```
