# FaxGetArchiveConfigurationW

- ea: `0x18000da10`
- end: `0x18000dcf7`
- name: `FaxGetArchiveConfigurationW`
- size: `743`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000d900`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000da10`
- `0x18002bb58`
- `0x180034538`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000db45`
- `RPCRT4!NdrClientCall3` at `0x18000db45`
- `KERNEL32!SetLastError` at `0x18000da89`
- `KERNEL32!SetLastError` at `0x18000dad1`
- `KERNEL32!SetLastError` at `0x18000dbb9`
- `KERNEL32!SetLastError` at `0x18000dc30`
- `KERNEL32!SetLastError` at `0x18000dcac`
- `KERNEL32!SetLastError` at `0x18000da89`
- `KERNEL32!SetLastError` at `0x18000dad1`
- `KERNEL32!SetLastError` at `0x18000dbb9`
- `KERNEL32!SetLastError` at `0x18000dc30`
- `KERNEL32!SetLastError` at `0x18000dcac`

## pseudocode

```c
__int64 __fastcall FaxGetArchiveConfigurationW(__int64 a1, unsigned int a2, LPVOID *a3)
{
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rax
  CLIENT_CALL_RETURN v9; // rax
  unsigned __int64 v10; // rcx
  unsigned int v11; // r8d
  _WORD *v12; // rcx
  unsigned int v13; // eax
  unsigned int v15; // [rsp+80h] [rbp+8h] BYREF
  LPVOID *v16; // [rsp+90h] [rbp+18h]
  CLIENT_CALL_RETURN v17; // [rsp+98h] [rbp+20h]

  v16 = a3;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
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
    v7 = 154;
LABEL_39:
    WPP_SF_(v6[2], v7, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
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
    v7 = 155;
    goto LABEL_39;
  }
  if ( a2 > 1 )
  {
    SetLastError(0x57u);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v7 = 156;
    goto LABEL_39;
  }
  *a3 = 0;
  v8 = *(_QWORD **)(a1 + 32);
  v17.Simple = 0;
  v9.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x29u, 0, *v8, a2, a3, &v15).Pointer;
  v17.Pointer = v9.Pointer;
  if ( LODWORD(v9.Pointer) )
  {
    SetLastError((DWORD)v9.Pointer);
  }
  else
  {
    if ( !(unsigned int)MarshallUpStructure(a3, &v15, &fax_archive_config_fields, 40, 1, 1) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
      }
      SetLastError(0x54Fu);
      pMemFree(*a3);
      *a3 = 0;
      return 0;
    }
    v10 = *((_QWORD *)*a3 + 1);
    v11 = v15;
    if ( v10 <= v15 )
    {
      if ( v10 )
      {
        *((_QWORD *)*a3 + 1) = (char *)*a3 + v10;
        v11 = v15;
      }
      v12 = (_WORD *)*((_QWORD *)*a3 + 1);
      if ( v12 )
      {
        v13 = (v11 + (unsigned int)*a3 - (_DWORD)v12) >> 1;
        if ( !v13 )
          return 0;
        while ( *v12 )
        {
          ++v12;
          if ( !--v13 )
            return 0;
        }
      }
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000da10  mov     rax, rsp
0x18000da13  mov     [rax+18h], r8
0x18000da17  push    rbx
0x18000da18  push    rsi
0x18000da19  push    rdi
0x18000da1a  push    r12
0x18000da1c  push    r15
0x18000da1e  sub     rsp, 50h
0x18000da22  mov     rsi, r8
0x18000da25  mov     r12d, edx
0x18000da28  mov     rbx, rcx
0x18000da2b  xor     edi, edi
0x18000da2d  mov     [rax+8], edi
0x18000da30  lea     r15, WPP_GLOBAL_Control
0x18000da37  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da3e  cmp     rcx, r15
0x18000da41  jz      short loc_18000DA67
0x18000da43  test    dword ptr [rcx+1Ch], 1000h
0x18000da4a  jz      short loc_18000DA67
0x18000da4c  cmp     byte ptr [rcx+19h], 5
0x18000da50  jb      short loc_18000DA67
0x18000da52  mov     edx, 99h
0x18000da57  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000da5e  mov     rcx, [rcx+10h]
0x18000da62  call    WPP_SF_
0x18000da67  test    rbx, rbx
0x18000da6a  jz      loc_18000DCA7
0x18000da70  cmp     [rbx], edi
0x18000da72  jz      loc_18000DCA7
0x18000da78  cmp     [rbx+10h], edi
0x18000da7b  jnz     loc_18000DCA7
0x18000da81  test    rsi, rsi
0x18000da84  jnz     short loc_18000DAC6
0x18000da86  lea     ecx, [rsi+57h]; dwErrCode
0x18000da89  call    cs:__imp_SetLastError
0x18000da90  nop     dword ptr [rax+rax+00h]
0x18000da95  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da9c  cmp     rcx, r15
0x18000da9f  jz      loc_18000DCE8
0x18000daa5  test    dword ptr [rcx+1Ch], 1000h
0x18000daac  jz      loc_18000DCE8
0x18000dab2  cmp     byte ptr [rcx+19h], 2
0x18000dab6  jb      loc_18000DCE8
0x18000dabc  mov     edx, 9Bh
0x18000dac1  jmp     loc_18000DCD8
0x18000dac6  cmp     r12d, 1
0x18000daca  jbe     short loc_18000DB0E
0x18000dacc  mov     ecx, 57h ; 'W'; dwErrCode
0x18000dad1  call    cs:__imp_SetLastError
0x18000dad8  nop     dword ptr [rax+rax+00h]
0x18000dadd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dae4  cmp     rcx, r15
0x18000dae7  jz      loc_18000DCE8
0x18000daed  test    dword ptr [rcx+1Ch], 1000h
0x18000daf4  jz      loc_18000DCE8
0x18000dafa  cmp     byte ptr [rcx+19h], 2
0x18000dafe  jb      loc_18000DCE8
0x18000db04  mov     edx, 9Ch
0x18000db09  jmp     loc_18000DCD8
0x18000db0e  mov     [rsi], rdi
0x18000db11  mov     rax, [rbx+20h]
0x18000db15  mov     [rsp+78h+arg_18], rdi
0x18000db1d  lea     rcx, [rsp+78h+arg_0]
0x18000db25  mov     [rsp+78h+var_48], rcx
0x18000db2a  mov     [rsp+78h+var_50], rsi
0x18000db2f  mov     [rsp+78h+var_58], r12d
0x18000db34  mov     r9, [rax]
0x18000db37  xor     r8d, r8d; pReturnValue
0x18000db3a  lea     edx, [r8+29h]; nProcNum
0x18000db3e  lea     rcx, pProxyInfo; pProxyInfo
0x18000db45  call    cs:__imp_NdrClientCall3
0x18000db4c  nop     dword ptr [rax+rax+00h]
0x18000db51  mov     rbx, rax
0x18000db54  mov     [rsp+78h+arg_18], rax
0x18000db5c  mov     [rsp+78h+var_38], eax
0x18000db60  jmp     short loc_18000DBB3
0x18000db62  mov     ebx, eax
0x18000db64  mov     [rsp+78h+var_38], eax
0x18000db68  lea     rdx, WPP_GLOBAL_Control
0x18000db6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db76  cmp     rcx, rdx
0x18000db79  jz      short loc_18000DBA2
0x18000db7b  test    dword ptr [rcx+1Ch], 1000h
0x18000db82  jz      short loc_18000DBA2
0x18000db84  cmp     byte ptr [rcx+19h], 2
0x18000db88  jb      short loc_18000DBA2
0x18000db8a  mov     edx, 9Dh
0x18000db8f  mov     r9d, eax
0x18000db92  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000db99  mov     rcx, [rcx+10h]
0x18000db9d  call    WPP_SF_d
0x18000dba2  xor     edi, edi
0x18000dba4  lea     r15, WPP_GLOBAL_Control
0x18000dbab  mov     rsi, [rsp+78h+arg_10]
0x18000dbb3  test    ebx, ebx
0x18000dbb5  jz      short loc_18000DBCA
0x18000dbb7  mov     ecx, ebx; dwErrCode
0x18000dbb9  call    cs:__imp_SetLastError
0x18000dbc0  nop     dword ptr [rax+rax+00h]
0x18000dbc5  jmp     loc_18000DCE8
0x18000dbca  mov     dword ptr [rsp+78h+var_50], 1
0x18000dbd2  mov     [rsp+78h+var_58], 1
0x18000dbda  mov     r9d, 28h ; '('
0x18000dbe0  lea     r8, ?fax_archive_config_fields@@3PAU_FieldInfo@@A; _FieldInfo near * fax_archive_config_fields
0x18000dbe7  lea     rdx, [rsp+78h+arg_0]
0x18000dbef  mov     rcx, rsi
0x18000dbf2  call    MarshallUpStructure
0x18000dbf7  test    eax, eax
0x18000dbf9  jnz     short loc_18000DC4C
0x18000dbfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc02  cmp     rcx, r15
0x18000dc05  jz      short loc_18000DC2B
0x18000dc07  test    dword ptr [rcx+1Ch], 1000h
0x18000dc0e  jz      short loc_18000DC2B
0x18000dc10  cmp     byte ptr [rcx+19h], 2
0x18000dc14  jb      short loc_18000DC2B
0x18000dc16  mov     edx, 9Eh
0x18000dc1b  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000dc22  mov     rcx, [rcx+10h]
0x18000dc26  call    WPP_SF_
0x18000dc2b  mov     ecx, 54Fh; dwErrCode
0x18000dc30  call    cs:__imp_SetLastError
0x18000dc37  nop     dword ptr [rax+rax+00h]
0x18000dc3c  mov     rcx, [rsi]; lpMem
0x18000dc3f  call    pMemFree
0x18000dc44  mov     [rsi], rdi
0x18000dc47  jmp     loc_18000DCE8
0x18000dc4c  mov     rdx, [rsi]
0x18000dc4f  mov     rcx, [rdx+8]
0x18000dc53  mov     r8d, [rsp+78h+arg_0]
0x18000dc5b  cmp     rcx, r8
0x18000dc5e  ja      loc_18000DCE8
0x18000dc64  test    rcx, rcx
0x18000dc67  jz      short loc_18000DC79
0x18000dc69  lea     rax, [rcx+rdx]
0x18000dc6d  mov     [rdx+8], rax
0x18000dc71  mov     r8d, [rsp+78h+arg_0]
0x18000dc79  mov     rdx, [rsi]
0x18000dc7c  mov     rcx, [rdx+8]
0x18000dc80  test    rcx, rcx
0x18000dc83  jz      short loc_18000DCA0
0x18000dc85  mov     eax, edx
0x18000dc87  sub     eax, ecx
0x18000dc89  add     eax, r8d
0x18000dc8c  shr     eax, 1
0x18000dc8e  jz      short loc_18000DCE8
0x18000dc90  cmp     di, [rcx]
0x18000dc93  jz      short loc_18000DCA0
0x18000dc95  add     rcx, 2
0x18000dc99  add     eax, 0FFFFFFFFh
0x18000dc9c  jnz     short loc_18000DC90
0x18000dc9e  jmp     short loc_18000DCE8
0x18000dca0  mov     eax, 1
0x18000dca5  jmp     short loc_18000DCEA
0x18000dca7  mov     ecx, 6; dwErrCode
0x18000dcac  call    cs:__imp_SetLastError
0x18000dcb3  nop     dword ptr [rax+rax+00h]
0x18000dcb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcbf  cmp     rcx, r15
0x18000dcc2  jz      short loc_18000DCE8
0x18000dcc4  test    dword ptr [rcx+1Ch], 1000h
0x18000dccb  jz      short loc_18000DCE8
0x18000dccd  cmp     byte ptr [rcx+19h], 2
0x18000dcd1  jb      short loc_18000DCE8
0x18000dcd3  mov     edx, 9Ah
0x18000dcd8  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000dcdf  mov     rcx, [rcx+10h]
0x18000dce3  call    WPP_SF_
0x18000dce8  xor     eax, eax
0x18000dcea  add     rsp, 50h
0x18000dcee  pop     r15
0x18000dcf0  pop     r12
0x18000dcf2  pop     rdi
0x18000dcf3  pop     rsi
0x18000dcf4  pop     rbx
0x18000dcf5  retn
```
