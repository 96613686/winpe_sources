# BHandleNT40CompatibleEscapes

- ea: `0x1800096c0`
- end: `0x180009825`
- name: `BHandleNT40CompatibleEscapes`
- size: `357`
- prototype: `__int64 __fastcall(_DWORD *, int, unsigned int, _WORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009100`
- `0x1800099ec`

## callees

- `0x1800096c0`
- `0x18001208c`
- `0x1800129f0`
- `0x180012a50`
- `0x18001758c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800097a9`
- `KERNEL32!SetLastError` at `0x180009806`
- `KERNEL32!SetLastError` at `0x1800097a9`
- `KERNEL32!SetLastError` at `0x180009806`

## pseudocode

```c
__int64 __fastcall BHandleNT40CompatibleEscapes(_DWORD *a1, int a2, unsigned int a3, _WORD *a4)
{
  unsigned int v5; // esi
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // ecx
  BOOL v11; // eax
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
            return OPSendOperator((__int64)a1, 0x21u);
          goto LABEL_30;
        }
        --a1[540];
        if ( !GSEndOptimization((__int64)a1) )
          return 0;
        v11 = GSSendGrestore((__int64)a1);
      }
      else
      {
        ++a1[540];
        if ( !GSEndOptimization((__int64)a1) || !GSSendGsave((__int64)a1) )
          return 0;
        v11 = OPSendOperator((__int64)a1, 0xFu);
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
0x1800096c0  mov     [rsp+arg_0], rbx
0x1800096c5  mov     [rsp+arg_8], rsi
0x1800096ca  push    rdi
0x1800096cb  sub     rsp, 20h
0x1800096cf  mov     rbx, rcx
0x1800096d2  mov     esi, 1
0x1800096d7  sub     edx, 26h ; '&'
0x1800096da  jz      loc_1800097C2
0x1800096e0  sub     edx, 0FDAh
0x1800096e6  jz      loc_1800097BA
0x1800096ec  sub     edx, esi
0x1800096ee  jz      short loc_180009703
0x1800096f0  cmp     edx, esi
0x1800096f2  jnz     loc_180009812
0x1800096f8  dec     dword ptr [rcx+86Ch]
0x1800096fe  jmp     loc_1800097A0
0x180009703  mov     ecx, [rcx+848h]
0x180009709  lea     eax, [rcx-2]
0x18000970c  cmp     eax, 5
0x18000970f  ja      loc_1800097A4
0x180009715  xor     edi, edi
0x180009717  test    r9, r9
0x18000971a  jz      loc_180009801
0x180009720  cmp     r8d, 2
0x180009724  jb      loc_180009801
0x18000972a  cmp     ecx, 3
0x18000972d  jle     short loc_1800097A4
0x18000972f  movzx   ecx, word ptr [r9]
0x180009733  test    ecx, ecx
0x180009735  jz      short loc_18000976F
0x180009737  sub     ecx, esi
0x180009739  jz      short loc_180009753
0x18000973b  cmp     ecx, esi
0x18000973d  jnz     loc_180009801
0x180009743  lea     edx, [rdi+21h]
0x180009746  mov     rcx, rbx
0x180009749  call    OPSendOperator
0x18000974e  jmp     loc_180009814
0x180009753  dec     dword ptr [rbx+870h]
0x180009759  mov     rcx, rbx
0x18000975c  call    GSEndOptimization
0x180009761  test    eax, eax
0x180009763  jz      short loc_18000979E
0x180009765  mov     rcx, rbx
0x180009768  call    GSSendGrestore
0x18000976d  jmp     short loc_18000979A
0x18000976f  add     [rbx+870h], esi
0x180009775  mov     rcx, rbx
0x180009778  call    GSEndOptimization
0x18000977d  test    eax, eax
0x18000977f  jz      short loc_18000979E
0x180009781  mov     rcx, rbx
0x180009784  call    GSSendGsave
0x180009789  test    eax, eax
0x18000978b  jz      short loc_18000979E
0x18000978d  mov     edx, 0Fh
0x180009792  mov     rcx, rbx
0x180009795  call    OPSendOperator
0x18000979a  test    eax, eax
0x18000979c  jnz     short loc_1800097A0
0x18000979e  mov     esi, edi
0x1800097a0  mov     eax, esi
0x1800097a2  jmp     short loc_180009814
0x1800097a4  mov     ecx, 32h ; '2'; dwErrCode
0x1800097a9  call    cs:__imp_SetLastError
0x1800097b0  nop     dword ptr [rax+rax+00h]
0x1800097b5  or      eax, 0FFFFFFFFh
0x1800097b8  jmp     short loc_180009814
0x1800097ba  add     [rcx+86Ch], esi
0x1800097c0  jmp     short loc_1800097A0
0x1800097c2  xor     edi, edi
0x1800097c4  test    r9, r9
0x1800097c7  jz      short loc_180009801
0x1800097c9  cmp     r8d, 2
0x1800097cd  jb      short loc_180009801
0x1800097cf  mov     eax, [rcx+868h]
0x1800097d5  cmp     [r9], di
0x1800097d9  jz      short loc_1800097E7
0x1800097db  bts     eax, 1Eh
0x1800097df  mov     [rcx+868h], eax
0x1800097e5  jmp     short loc_1800097A0
0x1800097e7  btr     eax, 1Eh
0x1800097eb  mov     [rcx+868h], eax
0x1800097f1  cmp     [rcx+2C0h], esi
0x1800097f7  jnz     short loc_1800097A0
0x1800097f9  or      [rcx+878h], esi
0x1800097ff  jmp     short loc_1800097A0
0x180009801  mov     ecx, 57h ; 'W'; dwErrCode
0x180009806  call    cs:__imp_SetLastError
0x18000980d  nop     dword ptr [rax+rax+00h]
0x180009812  xor     eax, eax
0x180009814  mov     rbx, [rsp+28h+arg_0]
0x180009819  mov     rsi, [rsp+28h+arg_8]
0x18000981e  add     rsp, 20h
0x180009822  pop     rdi
0x180009823  retn
```
