# BHandleNT40CompatibleEscapes

- ea: `0x1800093c4`
- end: `0x18000951c`
- name: `BHandleNT40CompatibleEscapes`
- size: `344`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008e40`
- `0x1800096d0`

## callees

- `0x1800093c4`
- `0x180011ae8`
- `0x18001241c`
- `0x18001247c`
- `0x180016e24`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800094ad`
- `KERNEL32!SetLastError` at `0x180009504`
- `KERNEL32!SetLastError` at `0x1800094ad`
- `KERNEL32!SetLastError` at `0x180009504`

## pseudocode

```c
__int64 __fastcall BHandleNT40CompatibleEscapes(_DWORD *a1, int a2, unsigned int a3, _WORD *a4)
{
  unsigned int v5; // esi
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // ecx
  int v11; // eax
  int v12; // eax

  v5 = 1;
  v6 = a2 - 38;
  if ( !v6 )
  {
    if ( a4 && a3 >= 2 )
    {
      v12 = a1[538];
      if ( *a4 )
      {
        a1[538] = v12 | 0x40000000;
      }
      else
      {
        a1[538] = v12 & 0xBFFFFFFF;
        if ( a1[176] == 1 )
          a1[542] |= 1u;
      }
      return v5;
    }
    goto LABEL_30;
  }
  v7 = v6 - 4058;
  if ( !v7 )
  {
    ++a1[539];
    return v5;
  }
  v8 = v7 - 1;
  if ( v8 )
  {
    if ( v8 == 1 )
    {
      --a1[539];
      return v5;
    }
    return 0;
  }
  v9 = a1[530];
  if ( (unsigned int)(v9 - 2) > 5 )
    goto LABEL_22;
  if ( a4 && a3 >= 2 )
  {
    if ( v9 > 3 )
    {
      if ( *a4 )
      {
        if ( *a4 != 1 )
        {
          if ( *a4 == 2 )
            return OPSendOperator(a1, 33);
          goto LABEL_30;
        }
        --a1[540];
        if ( !(unsigned int)GSEndOptimization(a1) )
          return 0;
        v11 = GSSendGrestore(a1);
      }
      else
      {
        ++a1[540];
        if ( !(unsigned int)GSEndOptimization(a1) || !(unsigned int)GSSendGsave(a1) )
          return 0;
        v11 = OPSendOperator(a1, 15);
      }
      if ( v11 )
        return v5;
      return 0;
    }
LABEL_22:
    SetLastError(0x32u);
    return 0xFFFFFFFFLL;
  }
LABEL_30:
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x1800093c4  mov     [rsp+arg_0], rbx
0x1800093c9  mov     [rsp+arg_8], rsi
0x1800093ce  push    rdi
0x1800093cf  sub     rsp, 20h
0x1800093d3  mov     rbx, rcx
0x1800093d6  mov     esi, 1
0x1800093db  sub     edx, 26h ; '&'
0x1800093de  jz      loc_1800094C0
0x1800093e4  sub     edx, 0FDAh
0x1800093ea  jz      loc_1800094B8
0x1800093f0  sub     edx, esi
0x1800093f2  jz      short loc_180009407
0x1800093f4  cmp     edx, esi
0x1800093f6  jnz     loc_18000950A
0x1800093fc  dec     dword ptr [rcx+86Ch]
0x180009402  jmp     loc_1800094A4
0x180009407  mov     ecx, [rcx+848h]
0x18000940d  lea     eax, [rcx-2]
0x180009410  cmp     eax, 5
0x180009413  ja      loc_1800094A8
0x180009419  xor     edi, edi
0x18000941b  test    r9, r9
0x18000941e  jz      loc_1800094FF
0x180009424  cmp     r8d, 2
0x180009428  jb      loc_1800094FF
0x18000942e  cmp     ecx, 3
0x180009431  jle     short loc_1800094A8
0x180009433  movzx   ecx, word ptr [r9]
0x180009437  test    ecx, ecx
0x180009439  jz      short loc_180009473
0x18000943b  sub     ecx, esi
0x18000943d  jz      short loc_180009457
0x18000943f  cmp     ecx, esi
0x180009441  jnz     loc_1800094FF
0x180009447  lea     edx, [rdi+21h]
0x18000944a  mov     rcx, rbx
0x18000944d  call    OPSendOperator
0x180009452  jmp     loc_18000950C
0x180009457  dec     dword ptr [rbx+870h]
0x18000945d  mov     rcx, rbx
0x180009460  call    GSEndOptimization
0x180009465  test    eax, eax
0x180009467  jz      short loc_1800094A2
0x180009469  mov     rcx, rbx
0x18000946c  call    GSSendGrestore
0x180009471  jmp     short loc_18000949E
0x180009473  add     [rbx+870h], esi
0x180009479  mov     rcx, rbx
0x18000947c  call    GSEndOptimization
0x180009481  test    eax, eax
0x180009483  jz      short loc_1800094A2
0x180009485  mov     rcx, rbx
0x180009488  call    GSSendGsave
0x18000948d  test    eax, eax
0x18000948f  jz      short loc_1800094A2
0x180009491  mov     edx, 0Fh
0x180009496  mov     rcx, rbx
0x180009499  call    OPSendOperator
0x18000949e  test    eax, eax
0x1800094a0  jnz     short loc_1800094A4
0x1800094a2  mov     esi, edi
0x1800094a4  mov     eax, esi
0x1800094a6  jmp     short loc_18000950C
0x1800094a8  mov     ecx, 32h ; '2'; dwErrCode
0x1800094ad  call    cs:__imp_SetLastError
0x1800094b3  or      eax, 0FFFFFFFFh
0x1800094b6  jmp     short loc_18000950C
0x1800094b8  add     [rcx+86Ch], esi
0x1800094be  jmp     short loc_1800094A4
0x1800094c0  xor     edi, edi
0x1800094c2  test    r9, r9
0x1800094c5  jz      short loc_1800094FF
0x1800094c7  cmp     r8d, 2
0x1800094cb  jb      short loc_1800094FF
0x1800094cd  mov     eax, [rcx+868h]
0x1800094d3  cmp     [r9], di
0x1800094d7  jz      short loc_1800094E5
0x1800094d9  bts     eax, 1Eh
0x1800094dd  mov     [rcx+868h], eax
0x1800094e3  jmp     short loc_1800094A4
0x1800094e5  btr     eax, 1Eh
0x1800094e9  mov     [rcx+868h], eax
0x1800094ef  cmp     [rcx+2C0h], esi
0x1800094f5  jnz     short loc_1800094A4
0x1800094f7  or      [rcx+878h], esi
0x1800094fd  jmp     short loc_1800094A4
0x1800094ff  mov     ecx, 57h ; 'W'; dwErrCode
0x180009504  call    cs:__imp_SetLastError
0x18000950a  xor     eax, eax
0x18000950c  mov     rbx, [rsp+28h+arg_0]
0x180009511  mov     rsi, [rsp+28h+arg_8]
0x180009516  add     rsp, 20h
0x18000951a  pop     rdi
0x18000951b  retn
```
