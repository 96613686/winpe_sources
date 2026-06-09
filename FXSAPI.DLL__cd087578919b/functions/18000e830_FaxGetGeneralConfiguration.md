# FaxGetGeneralConfiguration

- ea: `0x18000e830`
- end: `0x18000eb49`
- name: `FaxGetGeneralConfiguration`
- size: `793`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18000e830`
- `0x18002bb58`
- `0x180034538`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e974`
- `RPCRT4!NdrClientCall3` at `0x18000e974`
- `KERNEL32!SetLastError` at `0x18000e8ab`
- `KERNEL32!SetLastError` at `0x18000e903`
- `KERNEL32!SetLastError` at `0x18000e9e8`
- `KERNEL32!SetLastError` at `0x18000ea5a`
- `KERNEL32!SetLastError` at `0x18000eafe`
- `KERNEL32!SetLastError` at `0x18000e8ab`
- `KERNEL32!SetLastError` at `0x18000e903`
- `KERNEL32!SetLastError` at `0x18000e9e8`
- `KERNEL32!SetLastError` at `0x18000ea5a`
- `KERNEL32!SetLastError` at `0x18000eafe`

## pseudocode

```c
__int64 __fastcall FaxGetGeneralConfiguration(__int64 a1, unsigned int a2, LPVOID *a3)
{
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rax
  CLIENT_CALL_RETURN v9; // rax
  DWORD v10; // ecx
  unsigned int v11; // r9d
  char *v12; // rcx
  __int64 *v13; // r8
  __int64 v14; // rdx
  char *v15; // rax
  unsigned int v16; // ecx
  unsigned int v18; // [rsp+80h] [rbp+8h] BYREF
  LPVOID *v19; // [rsp+90h] [rbp+18h]
  CLIENT_CALL_RETURN v20; // [rsp+98h] [rbp+20h]

  v19 = a3;
  v18 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 341, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
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
    v7 = 342;
LABEL_45:
    WPP_SF_(v6[2], v7, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    return 0;
  }
  if ( a2 )
  {
    SetLastError(0x57u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 343, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids, a2);
    }
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
    v7 = 344;
    goto LABEL_45;
  }
  v8 = *(_QWORD **)(a1 + 32);
  v20.Simple = 0;
  v9.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x61u, 0, *v8, 0, a3, &v18).Pointer;
  v20.Pointer = v9.Pointer;
  if ( !LODWORD(v9.Pointer) )
  {
    if ( !(unsigned int)MarshallUpStructure(a3, &v18, &fax_general_config_fields, 88, 1, 1) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 346, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
      }
      v10 = 1359;
LABEL_26:
      SetLastError(v10);
      pMemFree(*a3);
      *a3 = 0;
      return 0;
    }
    v11 = v18;
    v12 = (char *)*a3;
    v13 = (__int64 *)((char *)*a3 + 8);
    v14 = *v13;
    if ( *v13 <= (unsigned __int64)v18 )
    {
      if ( v14 )
      {
        v15 = &v12[v14];
        *v13 = (__int64)&v12[v14];
      }
      else
      {
        v15 = 0;
      }
      if ( !v15 )
        return 1;
      v16 = (v11 + (_DWORD)v12 - *(_DWORD *)v13) >> 1;
      if ( v16 )
      {
        while ( *(_WORD *)v15 )
        {
          v15 += 2;
          if ( !--v16 )
            goto LABEL_35;
        }
        return 1;
      }
    }
LABEL_35:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 347, &WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids);
    }
    v10 = 13;
    goto LABEL_26;
  }
  SetLastError((DWORD)v9.Pointer);
  return 0;
}

```

## disassembly

```asm
0x18000e830  mov     rax, rsp
0x18000e833  mov     [rax+18h], r8
0x18000e837  push    rbx
0x18000e838  push    rsi
0x18000e839  push    rdi
0x18000e83a  push    r12
0x18000e83c  push    r15
0x18000e83e  sub     rsp, 50h
0x18000e842  mov     rsi, r8
0x18000e845  mov     r12d, edx
0x18000e848  mov     rbx, rcx
0x18000e84b  xor     edi, edi
0x18000e84d  mov     [rax+8], edi
0x18000e850  lea     r15, WPP_GLOBAL_Control
0x18000e857  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e85e  cmp     rcx, r15
0x18000e861  jz      short loc_18000E887
0x18000e863  test    dword ptr [rcx+1Ch], 1000h
0x18000e86a  jz      short loc_18000E887
0x18000e86c  cmp     byte ptr [rcx+19h], 5
0x18000e870  jb      short loc_18000E887
0x18000e872  mov     edx, 155h
0x18000e877  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000e87e  mov     rcx, [rcx+10h]
0x18000e882  call    WPP_SF_
0x18000e887  test    rbx, rbx
0x18000e88a  jz      loc_18000EAF9
0x18000e890  cmp     [rbx], edi
0x18000e892  jz      loc_18000EAF9
0x18000e898  cmp     [rbx+10h], edi
0x18000e89b  jnz     loc_18000EAF9
0x18000e8a1  test    r12d, r12d
0x18000e8a4  jz      short loc_18000E8FB
0x18000e8a6  mov     ecx, 57h ; 'W'; dwErrCode
0x18000e8ab  call    cs:__imp_SetLastError
0x18000e8b2  nop     dword ptr [rax+rax+00h]
0x18000e8b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8be  cmp     rcx, r15
0x18000e8c1  jz      loc_18000EB3A
0x18000e8c7  test    dword ptr [rcx+1Ch], 1000h
0x18000e8ce  jz      loc_18000EB3A
0x18000e8d4  cmp     byte ptr [rcx+19h], 2
0x18000e8d8  jb      loc_18000EB3A
0x18000e8de  mov     edx, 157h
0x18000e8e3  mov     r9d, r12d
0x18000e8e6  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000e8ed  mov     rcx, [rcx+10h]
0x18000e8f1  call    WPP_SF_d
0x18000e8f6  jmp     loc_18000EB3A
0x18000e8fb  test    rsi, rsi
0x18000e8fe  jnz     short loc_18000E940
0x18000e900  lea     ecx, [rsi+57h]; dwErrCode
0x18000e903  call    cs:__imp_SetLastError
0x18000e90a  nop     dword ptr [rax+rax+00h]
0x18000e90f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e916  cmp     rcx, r15
0x18000e919  jz      loc_18000EB3A
0x18000e91f  test    dword ptr [rcx+1Ch], 1000h
0x18000e926  jz      loc_18000EB3A
0x18000e92c  cmp     byte ptr [rcx+19h], 2
0x18000e930  jb      loc_18000EB3A
0x18000e936  mov     edx, 158h
0x18000e93b  jmp     loc_18000EB2A
0x18000e940  mov     rax, [rbx+20h]
0x18000e944  mov     [rsp+78h+arg_18], rdi
0x18000e94c  lea     rcx, [rsp+78h+arg_0]
0x18000e954  mov     [rsp+78h+var_48], rcx
0x18000e959  mov     [rsp+78h+var_50], rsi
0x18000e95e  mov     [rsp+78h+var_58], r12d
0x18000e963  mov     r9, [rax]
0x18000e966  xor     r8d, r8d; pReturnValue
0x18000e969  lea     edx, [r8+61h]; nProcNum
0x18000e96d  lea     rcx, pProxyInfo; pProxyInfo
0x18000e974  call    cs:__imp_NdrClientCall3
0x18000e97b  nop     dword ptr [rax+rax+00h]
0x18000e980  mov     rbx, rax
0x18000e983  mov     [rsp+78h+arg_18], rax
0x18000e98b  mov     [rsp+78h+var_38], eax
0x18000e98f  jmp     short loc_18000E9E2
0x18000e991  mov     ebx, eax
0x18000e993  mov     [rsp+78h+var_38], eax
0x18000e997  lea     rdx, WPP_GLOBAL_Control
0x18000e99e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9a5  cmp     rcx, rdx
0x18000e9a8  jz      short loc_18000E9D1
0x18000e9aa  test    dword ptr [rcx+1Ch], 1000h
0x18000e9b1  jz      short loc_18000E9D1
0x18000e9b3  cmp     byte ptr [rcx+19h], 2
0x18000e9b7  jb      short loc_18000E9D1
0x18000e9b9  mov     edx, 159h
0x18000e9be  mov     r9d, eax
0x18000e9c1  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000e9c8  mov     rcx, [rcx+10h]
0x18000e9cc  call    WPP_SF_d
0x18000e9d1  xor     edi, edi
0x18000e9d3  lea     r15, WPP_GLOBAL_Control
0x18000e9da  mov     rsi, [rsp+78h+arg_10]
0x18000e9e2  test    ebx, ebx
0x18000e9e4  jz      short loc_18000E9F9
0x18000e9e6  mov     ecx, ebx; dwErrCode
0x18000e9e8  call    cs:__imp_SetLastError
0x18000e9ef  nop     dword ptr [rax+rax+00h]
0x18000e9f4  jmp     loc_18000EB3A
0x18000e9f9  mov     ebx, 1
0x18000e9fe  mov     dword ptr [rsp+78h+var_50], ebx
0x18000ea02  mov     [rsp+78h+var_58], ebx
0x18000ea06  lea     r9d, [rbx+57h]
0x18000ea0a  lea     r8, ?fax_general_config_fields@@3PAU_FieldInfo@@A; _FieldInfo near * fax_general_config_fields
0x18000ea11  lea     rdx, [rsp+78h+arg_0]
0x18000ea19  mov     rcx, rsi
0x18000ea1c  call    MarshallUpStructure
0x18000ea21  test    eax, eax
0x18000ea23  jnz     short loc_18000EA76
0x18000ea25  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea2c  cmp     rcx, r15
0x18000ea2f  jz      short loc_18000EA55
0x18000ea31  test    dword ptr [rcx+1Ch], 1000h
0x18000ea38  jz      short loc_18000EA55
0x18000ea3a  cmp     byte ptr [rcx+19h], 2
0x18000ea3e  jb      short loc_18000EA55
0x18000ea40  mov     edx, 15Ah
0x18000ea45  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000ea4c  mov     rcx, [rcx+10h]
0x18000ea50  call    WPP_SF_
0x18000ea55  mov     ecx, 54Fh; dwErrCode
0x18000ea5a  call    cs:__imp_SetLastError
0x18000ea61  nop     dword ptr [rax+rax+00h]
0x18000ea66  mov     rcx, [rsi]; lpMem
0x18000ea69  call    pMemFree
0x18000ea6e  mov     [rsi], rdi
0x18000ea71  jmp     loc_18000EB3A
0x18000ea76  mov     r9d, [rsp+78h+arg_0]
0x18000ea7e  mov     rcx, [rsi]
0x18000ea81  lea     r8, [rcx+8]
0x18000ea85  mov     rdx, [r8]
0x18000ea88  cmp     rdx, r9
0x18000ea8b  ja      short loc_18000EABB
0x18000ea8d  test    rdx, rdx
0x18000ea90  jz      short loc_18000EA9B
0x18000ea92  lea     rax, [rdx+rcx]
0x18000ea96  mov     [r8], rax
0x18000ea99  jmp     short loc_18000EA9E
0x18000ea9b  mov     rax, rdi
0x18000ea9e  test    rax, rax
0x18000eaa1  jz      short loc_18000EAF5
0x18000eaa3  sub     ecx, [r8]
0x18000eaa6  add     ecx, r9d
0x18000eaa9  shr     ecx, 1
0x18000eaab  jz      short loc_18000EABB
0x18000eaad  cmp     di, [rax]
0x18000eab0  jz      short loc_18000EAF5
0x18000eab2  add     rax, 2
0x18000eab6  add     ecx, 0FFFFFFFFh
0x18000eab9  jnz     short loc_18000EAAD
0x18000eabb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eac2  cmp     rcx, r15
0x18000eac5  jz      short loc_18000EAEB
0x18000eac7  test    dword ptr [rcx+1Ch], 1000h
0x18000eace  jz      short loc_18000EAEB
0x18000ead0  cmp     byte ptr [rcx+19h], 2
0x18000ead4  jb      short loc_18000EAEB
0x18000ead6  mov     edx, 15Bh
0x18000eadb  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000eae2  mov     rcx, [rcx+10h]
0x18000eae6  call    WPP_SF_
0x18000eaeb  mov     ecx, 0Dh
0x18000eaf0  jmp     loc_18000EA5A
0x18000eaf5  mov     eax, ebx
0x18000eaf7  jmp     short loc_18000EB3C
0x18000eaf9  mov     ecx, 6; dwErrCode
0x18000eafe  call    cs:__imp_SetLastError
0x18000eb05  nop     dword ptr [rax+rax+00h]
0x18000eb0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb11  cmp     rcx, r15
0x18000eb14  jz      short loc_18000EB3A
0x18000eb16  test    dword ptr [rcx+1Ch], 1000h
0x18000eb1d  jz      short loc_18000EB3A
0x18000eb1f  cmp     byte ptr [rcx+19h], 2
0x18000eb23  jb      short loc_18000EB3A
0x18000eb25  mov     edx, 156h
0x18000eb2a  lea     r8, WPP_6aa9d578c4393c02b9eb8137eb0c030f_Traceguids
0x18000eb31  mov     rcx, [rcx+10h]
0x18000eb35  call    WPP_SF_
0x18000eb3a  xor     eax, eax
0x18000eb3c  add     rsp, 50h
0x18000eb40  pop     r15
0x18000eb42  pop     r12
0x18000eb44  pop     rdi
0x18000eb45  pop     rsi
0x18000eb46  pop     rbx
0x18000eb47  retn
```
