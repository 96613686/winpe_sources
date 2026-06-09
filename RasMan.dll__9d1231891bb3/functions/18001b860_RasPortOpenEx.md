# RasPortOpenEx

- ea: `0x18001b860`
- end: `0x18001ba5e`
- name: `RasPortOpenEx`
- size: `510`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x180001c70`
- `0x180002f80`
- `0x18001b860`
- `0x18001fb60`
- `0x180020fd8`
- `0x180021000`
- `0x1800213e4`
- `0x180024d88`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b9f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b9f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b974`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b974`

## pseudocode

```c
__int64 __fastcall RasPortOpenEx(__int64 a1, unsigned int a2, _QWORD *a3, __int64 a4, __int64 a5)
{
  unsigned int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  __int64 v12; // r9
  int v13; // ebx
  PVOID *v14; // rcx
  HLOCAL v15; // rax
  void *v16; // rbx
  unsigned int UserSid; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rdx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  v9 = SubmitLocalRequest(0x61u, a1, a2, a4, 1, a5, a3);
  v10 = v9;
  if ( v9
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
  }
  v11 = IsRasmanProcess();
  v13 = v11;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    LOBYTE(v12) = v11 != 0;
    WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v12);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 )
    goto LABEL_35;
  if ( v13 && !NtCurrentTeb()->IsImpersonating )
    goto LABEL_34;
  v15 = LocalAlloc(0x40u, 0x1388u);
  v16 = v15;
  if ( v15 )
  {
    UserSid = GetUserSid((__int64)v15);
    if ( UserSid )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_29;
      }
      v19 = 98;
    }
    else
    {
      UserSid = RasSetPortUserData(*a3, 8, v16, 5000);
      if ( !UserSid )
        goto LABEL_29;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_29;
      }
      v19 = 97;
    }
    WPP_SF_d(v18[2], v19, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, UserSid);
LABEL_29:
    LocalFree(v16);
LABEL_34:
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_35;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    goto LABEL_34;
  }
LABEL_35:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x40) != 0 && *((_BYTE *)v14 + 25) >= 6u )
    WPP_SF_d(v14[2], 100, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18001b860  push    rbx
0x18001b862  push    rsi
0x18001b863  push    rdi
0x18001b864  push    r12
0x18001b866  push    r14
0x18001b868  push    r15
0x18001b86a  sub     rsp, 48h
0x18001b86e  mov     rbx, r9
0x18001b871  mov     r14, r8
0x18001b874  mov     edi, edx
0x18001b876  mov     rsi, rcx
0x18001b879  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b880  lea     r15, WPP_GLOBAL_Control
0x18001b887  lea     r12, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001b88e  cmp     rcx, r15
0x18001b891  jz      short loc_18001B8B0
0x18001b893  test    byte ptr [rcx+1Ch], 40h
0x18001b897  jz      short loc_18001B8B0
0x18001b899  cmp     byte ptr [rcx+19h], 6
0x18001b89d  jb      short loc_18001B8B0
0x18001b89f  mov     rcx, [rcx+10h]
0x18001b8a3  mov     edx, 5Eh ; '^'
0x18001b8a8  mov     r8, r12
0x18001b8ab  call    WPP_SF_
0x18001b8b0  mov     rax, [rsp+78h+arg_20]
0x18001b8b8  mov     ecx, 61h ; 'a'
0x18001b8bd  mov     [rsp+78h+var_48], r14
0x18001b8c2  mov     r9, rbx
0x18001b8c5  mov     [rsp+78h+var_50], rax
0x18001b8ca  mov     r8d, edi
0x18001b8cd  mov     rdx, rsi
0x18001b8d0  mov     [rsp+78h+var_58], 1
0x18001b8d8  call    SubmitLocalRequest
0x18001b8dd  mov     edi, eax
0x18001b8df  test    eax, eax
0x18001b8e1  jz      short loc_18001B90F
0x18001b8e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8ea  cmp     rcx, r15
0x18001b8ed  jz      short loc_18001B90F
0x18001b8ef  test    byte ptr [rcx+1Ch], 40h
0x18001b8f3  jz      short loc_18001B90F
0x18001b8f5  cmp     byte ptr [rcx+19h], 2
0x18001b8f9  jb      short loc_18001B90F
0x18001b8fb  mov     rcx, [rcx+10h]
0x18001b8ff  mov     edx, 5Fh ; '_'
0x18001b904  mov     r9d, eax
0x18001b907  mov     r8, r12
0x18001b90a  call    WPP_SF_d
0x18001b90f  call    IsRasmanProcess
0x18001b914  mov     ebx, eax
0x18001b916  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b91d  cmp     rcx, r15
0x18001b920  jz      short loc_18001B94C
0x18001b922  test    byte ptr [rcx+1Ch], 40h
0x18001b926  jz      short loc_18001B94C
0x18001b928  cmp     byte ptr [rcx+19h], 5
0x18001b92c  jb      short loc_18001B94C
0x18001b92e  mov     rcx, [rcx+10h]
0x18001b932  test    eax, eax
0x18001b934  mov     edx, 60h ; '`'
0x18001b939  mov     r8, r12
0x18001b93c  setnz   r9b
0x18001b940  call    WPP_SF_c
0x18001b945  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b94c  test    edi, edi
0x18001b94e  jnz     loc_18001BA29
0x18001b954  test    ebx, ebx
0x18001b956  jz      short loc_18001B968
0x18001b958  mov     eax, gs:179Ch
0x18001b960  test    eax, eax
0x18001b962  jz      loc_18001BA22
0x18001b968  mov     esi, 1388h
0x18001b96d  mov     ecx, 40h ; '@'; uFlags
0x18001b972  mov     edx, esi; uBytes
0x18001b974  call    cs:__imp_LocalAlloc
0x18001b97a  mov     rbx, rax
0x18001b97d  test    rax, rax
0x18001b980  jz      short loc_18001B9F9
0x18001b982  mov     rcx, rax
0x18001b985  call    GetUserSid
0x18001b98a  test    eax, eax
0x18001b98c  jnz     short loc_18001B9C2
0x18001b98e  mov     rcx, [r14]
0x18001b991  lea     edx, [rax+8]
0x18001b994  mov     r9d, esi
0x18001b997  mov     r8, rbx
0x18001b99a  call    RasSetPortUserData
0x18001b99f  test    eax, eax
0x18001b9a1  jz      short loc_18001B9EE
0x18001b9a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9aa  cmp     rcx, r15
0x18001b9ad  jz      short loc_18001B9EE
0x18001b9af  test    byte ptr [rcx+1Ch], 40h
0x18001b9b3  jz      short loc_18001B9EE
0x18001b9b5  cmp     byte ptr [rcx+19h], 2
0x18001b9b9  jb      short loc_18001B9EE
0x18001b9bb  mov     edx, 61h ; 'a'
0x18001b9c0  jmp     short loc_18001B9DF
0x18001b9c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9c9  cmp     rcx, r15
0x18001b9cc  jz      short loc_18001B9EE
0x18001b9ce  test    byte ptr [rcx+1Ch], 40h
0x18001b9d2  jz      short loc_18001B9EE
0x18001b9d4  cmp     byte ptr [rcx+19h], 2
0x18001b9d8  jb      short loc_18001B9EE
0x18001b9da  mov     edx, 62h ; 'b'
0x18001b9df  mov     rcx, [rcx+10h]
0x18001b9e3  mov     r9d, eax
0x18001b9e6  mov     r8, r12
0x18001b9e9  call    WPP_SF_d
0x18001b9ee  mov     rcx, rbx; hMem
0x18001b9f1  call    cs:__imp_LocalFree
0x18001b9f7  jmp     short loc_18001BA22
0x18001b9f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba00  cmp     rcx, r15
0x18001ba03  jz      short loc_18001BA4E
0x18001ba05  test    byte ptr [rcx+1Ch], 40h
0x18001ba09  jz      short loc_18001BA29
0x18001ba0b  cmp     byte ptr [rcx+19h], 3
0x18001ba0f  jb      short loc_18001BA29
0x18001ba11  mov     rcx, [rcx+10h]
0x18001ba15  mov     edx, 63h ; 'c'
0x18001ba1a  mov     r8, r12
0x18001ba1d  call    WPP_SF_
0x18001ba22  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba29  cmp     rcx, r15
0x18001ba2c  jz      short loc_18001BA4E
0x18001ba2e  test    byte ptr [rcx+1Ch], 40h
0x18001ba32  jz      short loc_18001BA4E
0x18001ba34  cmp     byte ptr [rcx+19h], 6
0x18001ba38  jb      short loc_18001BA4E
0x18001ba3a  mov     rcx, [rcx+10h]
0x18001ba3e  mov     edx, 64h ; 'd'
0x18001ba43  mov     r9d, edi
0x18001ba46  mov     r8, r12
0x18001ba49  call    WPP_SF_d
0x18001ba4e  mov     eax, edi
0x18001ba50  add     rsp, 48h
0x18001ba54  pop     r15
0x18001ba56  pop     r14
0x18001ba58  pop     r12
0x18001ba5a  pop     rdi
0x18001ba5b  pop     rsi
0x18001ba5c  pop     rbx
0x18001ba5d  retn
```
