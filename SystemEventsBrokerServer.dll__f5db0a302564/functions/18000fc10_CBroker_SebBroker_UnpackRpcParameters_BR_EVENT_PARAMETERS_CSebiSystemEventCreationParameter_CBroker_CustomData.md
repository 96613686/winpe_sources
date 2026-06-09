# CBroker::SebBroker::UnpackRpcParameters(_BR_EVENT_PARAMETERS *,_CSebiSystemEventCreationParameter &,CBroker::_CustomData * *)

- ea: `0x18000fc10`
- end: `0x180010551`
- name: `?UnpackRpcParameters@SebBroker@CBroker@@CAXPEAU_BR_EVENT_PARAMETERS@@AEAU_CSebiSystemEventCreationParameter@@PEAPEAU_CustomData@2@@Z`
- size: `2369`
- prototype: `void __fastcall(struct _BR_EVENT_PARAMETERS *, struct _CSebiSystemEventCreationParameter *, struct CBroker::_CustomData **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f680`

## callees

- `0x18000fc10`
- `0x18001cf74`
- `0x18001d39c`
- `0x18001d9ac`
- `0x180022440`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fce2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fd32`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fd87`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fdda`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fe31`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fe86`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fedb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ff7d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fffb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800100b8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fce2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fd32`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fd87`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fdda`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fe31`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fe86`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fedb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ff7d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000fffb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800100b8`

## pseudocode

```c
void __fastcall CBroker::SebBroker::UnpackRpcParameters(
        struct _BR_EVENT_PARAMETERS *a1,
        struct _CSebiSystemEventCreationParameter *a2,
        void ***a3)
{
  char v6; // r13
  char v7; // r15
  unsigned int v8; // r14d
  __int64 v9; // rsi
  const WCHAR *v10; // r8
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  struct CBroker::_CustomData *v18; // rax
  struct CBroker::_CustomData *v19; // rax
  __int64 v20; // rax
  int *v21; // rcx
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rax
  void **pExceptionObject; // [rsp+30h] [rbp-28h] BYREF
  __int128 v29; // [rsp+38h] [rbp-20h]
  int v30; // [rsp+48h] [rbp-10h]

  if ( *(_WORD *)a1 && !*((_QWORD *)a1 + 1) )
  {
    v30 = 4;
    pExceptionObject = &Broker::InvalidParameter::`vftable';
    v29 = 0;
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
  *(_OWORD *)a2 = 0;
  *((_OWORD *)a2 + 1) = 0;
  v6 = 0;
  *((_OWORD *)a2 + 2) = 0;
  v7 = 0;
  *((_QWORD *)a2 + 6) = 0;
  *a3 = 0;
  v8 = 0;
  while ( v8 < *(unsigned __int16 *)a1 )
  {
    v9 = 32LL * v8;
    v10 = *(const WCHAR **)(v9 + *((_QWORD *)a1 + 1));
    if ( !v10 )
    {
      v30 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v29 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    v11 = CompareStringW(0x7Fu, 1u, v10, -1, L"Type", -1);
    v12 = *((_QWORD *)a1 + 1);
    if ( v11 == 2 )
    {
      if ( *(_DWORD *)(v12 + v9 + 8) )
      {
        v30 = 4;
        pExceptionObject = &Broker::InvalidParameter::`vftable';
        v29 = 0;
        throw (Broker::InvalidParameter *)&pExceptionObject;
      }
      ++v8;
      *((_DWORD *)a2 + 2) = *(_DWORD *)(v12 + v9 + 16);
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v12 + 32LL * v8), -1, L"TriggerType", -1) == 2 )
      {
        v13 = *((_QWORD *)a1 + 1);
        if ( *(_DWORD *)(v13 + v9 + 8) )
        {
          v30 = 4;
          pExceptionObject = &Broker::InvalidParameter::`vftable';
          v29 = 0;
          throw (Broker::InvalidParameter *)&pExceptionObject;
        }
        v7 = 1;
        *((_DWORD *)a2 + 3) = *(_DWORD *)(v13 + v9 + 16);
        goto LABEL_70;
      }
      if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(*((_QWORD *)a1 + 1) + 32LL * v8), -1, L"EventName", -1) == 2 )
      {
        v14 = *((_QWORD *)a1 + 1);
        if ( *(_DWORD *)(v14 + v9 + 8) != 1 )
        {
          v30 = 4;
          pExceptionObject = &Broker::InvalidParameter::`vftable';
          v29 = 0;
          throw (Broker::InvalidParameter *)&pExceptionObject;
        }
        *(_QWORD *)a2 = *(_QWORD *)(v14 + v9 + 16);
        goto LABEL_70;
      }
      if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(*((_QWORD *)a1 + 1) + 32LL * v8), -1, L"OneShot", -1) == 2 )
      {
        v15 = *((_QWORD *)a1 + 1);
        if ( *(_DWORD *)(v15 + v9 + 8) )
        {
          v30 = 4;
          pExceptionObject = &Broker::InvalidParameter::`vftable';
          v29 = 0;
          throw (Broker::InvalidParameter *)&pExceptionObject;
        }
        *((_DWORD *)a2 + 6) = *(_DWORD *)(v15 + v9 + 16) != 0;
        goto LABEL_70;
      }
      if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(*((_QWORD *)a1 + 1) + 32LL * v8), -1, L"Operator", -1) == 2 )
      {
        v16 = *((_QWORD *)a1 + 1);
        if ( *(_DWORD *)(v16 + v9 + 8) )
        {
          v30 = 4;
          pExceptionObject = &Broker::InvalidParameter::`vftable';
          v29 = 0;
          throw (Broker::InvalidParameter *)&pExceptionObject;
        }
        ++v8;
        *((_DWORD *)a2 + 4) = *(_DWORD *)(v16 + v9 + 16);
      }
      else if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(*((_QWORD *)a1 + 1) + 32LL * v8), -1, L"Value", -1) == 2 )
      {
        v17 = *((_QWORD *)a1 + 1);
        if ( *(_DWORD *)(v17 + v9 + 8) )
        {
          v30 = 4;
          pExceptionObject = &Broker::InvalidParameter::`vftable';
          v29 = 0;
          throw (Broker::InvalidParameter *)&pExceptionObject;
        }
        ++v8;
        *((_DWORD *)a2 + 5) = *(_DWORD *)(v17 + v9 + 16);
      }
      else
      {
        if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(*((_QWORD *)a1 + 1) + 32LL * v8), -1, L"Data", -1) == 2 )
        {
          if ( *(_DWORD *)(*((_QWORD *)a1 + 1) + v9 + 8) != 4 )
          {
            v30 = 4;
            pExceptionObject = &Broker::InvalidParameter::`vftable';
            v29 = 0;
            throw (Broker::InvalidParameter *)&pExceptionObject;
          }
          if ( !*a3 )
          {
            v18 = (struct CBroker::_CustomData *)operator new(0x10u);
            *a3 = (void **)v18;
            *(_OWORD *)v18 = 0;
          }
          *((_DWORD *)*a3 + 2) = *(unsigned __int16 *)(*((_QWORD *)a1 + 1) + v9 + 16);
          **a3 = operator new[](*((unsigned int *)*a3 + 2));
          memcpy_0(**a3, *(const void **)(*((_QWORD *)a1 + 1) + v9 + 24), *((unsigned int *)*a3 + 2));
        }
        else if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(*((_QWORD *)a1 + 1) + 32LL * v8), -1, L"Offset", -1) == 2 )
        {
          if ( *(_DWORD *)(*((_QWORD *)a1 + 1) + v9 + 8) )
          {
            v30 = 4;
            pExceptionObject = &Broker::InvalidParameter::`vftable';
            v29 = 0;
            throw (Broker::InvalidParameter *)&pExceptionObject;
          }
          if ( !*a3 )
          {
            v19 = (struct CBroker::_CustomData *)operator new(0x10u);
            *a3 = (void **)v19;
            *(_OWORD *)v19 = 0;
          }
          *((_DWORD *)*a3 + 3) = *(_DWORD *)(*((_QWORD *)a1 + 1) + v9 + 16);
        }
        else
        {
          if ( v6 )
            goto LABEL_86;
          if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(*((_QWORD *)a1 + 1) + 32LL * v8), -1, L"TriggerOptions", -1) == 2 )
          {
            v20 = *((_QWORD *)a1 + 1);
            if ( *(_DWORD *)(v20 + v9 + 8) != 4 )
            {
              v30 = 4;
              pExceptionObject = &Broker::InvalidParameter::`vftable';
              v29 = 0;
              throw (Broker::InvalidParameter *)&pExceptionObject;
            }
            if ( *(_WORD *)(v20 + v9 + 16) != 16 )
            {
              v30 = 4;
              pExceptionObject = &Broker::InvalidParameter::`vftable';
              v29 = 0;
              throw (Broker::InvalidParameter *)&pExceptionObject;
            }
            v21 = *(int **)(v20 + v9 + 24);
            v22 = *v21;
            if ( *v21 )
            {
              switch ( v22 )
              {
                case 1:
                  *((_DWORD *)a2 + 7) = 32;
                  break;
                case 2:
                  *((_DWORD *)a2 + 7) = 128;
                  break;
                case 3:
                  *((_DWORD *)a2 + 7) = 0x8000;
                  break;
                default:
                  v30 = 4;
                  pExceptionObject = &Broker::InvalidParameter::`vftable';
                  v29 = 0;
                  throw (Broker::InvalidParameter *)&pExceptionObject;
              }
            }
            else
            {
              *((_DWORD *)a2 + 7) = 0;
            }
            if ( *((_BYTE *)v21 + 4) )
              *((_DWORD *)a2 + 8) = 1;
            if ( *((_BYTE *)v21 + 5) )
              *((_DWORD *)a2 + 9) = 1;
            *((_DWORD *)a2 + 10) = v21[2];
            *((_DWORD *)a2 + 11) = v21[3];
          }
          else
          {
            if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(*((_QWORD *)a1 + 1) + 32LL * v8), -1, L"CSebTriggerOptions", -1) != 2 )
            {
LABEL_86:
              v30 = 4;
              pExceptionObject = &Broker::InvalidParameter::`vftable';
              v29 = 0;
              throw (Broker::InvalidParameter *)&pExceptionObject;
            }
            v23 = *((_QWORD *)a1 + 1);
            if ( *(_DWORD *)(v23 + v9 + 8) != 4 )
            {
              v30 = 4;
              pExceptionObject = &Broker::InvalidParameter::`vftable';
              v29 = 0;
              throw (Broker::InvalidParameter *)&pExceptionObject;
            }
            if ( *(_WORD *)(v23 + v9 + 16) != 28 )
            {
              v30 = 4;
              pExceptionObject = &Broker::InvalidParameter::`vftable';
              v29 = 0;
              throw (Broker::InvalidParameter *)&pExceptionObject;
            }
            v24 = *(_QWORD *)(v23 + v9 + 24);
            if ( *(_DWORD *)v24 != 1 )
            {
              v30 = 4;
              pExceptionObject = &Broker::InvalidParameter::`vftable';
              v29 = 0;
              throw (Broker::InvalidParameter *)&pExceptionObject;
            }
            v25 = *(_DWORD *)(v24 + 4);
            if ( v25 )
            {
              switch ( v25 )
              {
                case 1:
                  *((_DWORD *)a2 + 7) = 32;
                  break;
                case 2:
                  *((_DWORD *)a2 + 7) = 128;
                  break;
                case 3:
                  *((_DWORD *)a2 + 7) = 0x8000;
                  break;
                default:
                  v30 = 4;
                  pExceptionObject = &Broker::InvalidParameter::`vftable';
                  v29 = 0;
                  throw (Broker::InvalidParameter *)&pExceptionObject;
              }
            }
            else
            {
              *((_DWORD *)a2 + 7) = 0;
            }
            if ( *(_BYTE *)(v24 + 8) )
              *((_DWORD *)a2 + 8) = 1;
            if ( *(_BYTE *)(v24 + 9) )
              *((_DWORD *)a2 + 9) = 1;
            *((_DWORD *)a2 + 10) = *(_DWORD *)(v24 + 12);
            *((_DWORD *)a2 + 11) = *(_DWORD *)(v24 + 16);
            *((_DWORD *)a2 + 12) = *(_DWORD *)(v24 + 20);
            *((_DWORD *)a2 + 13) = *(_DWORD *)(v24 + 24);
          }
          v6 = 1;
        }
LABEL_70:
        ++v8;
      }
    }
  }
  v26 = *((int *)a2 + 2);
  if ( (unsigned int)(v26 - 4096) > 0x42 )
  {
    v30 = 4;
    pExceptionObject = &Broker::InvalidParameter::`vftable';
    v29 = 0;
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
  if ( !v7 )
    *((_DWORD *)a2 + 3) = *((_DWORD *)&CBroker::EventPolicyTable + 10 * v26 - 40956);
  if ( (_DWORD)v26 == 4124 || (_DWORD)v26 == 4148 )
  {
    if ( !*(_QWORD *)a2 )
    {
      v30 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v29 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
  }
  else
  {
    v27 = 40 * (v26 - 4096);
    if ( !*(_DWORD *)((char *)&CBroker::EventPolicyTable + v27 + 4)
      && !*(_DWORD *)((char *)&CBroker::EventPolicyTable + v27 + 8) )
    {
      v30 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v29 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
    *(_QWORD *)a2 = *(struct CBroker::_EventPolicy near **)((char *)&CBroker::EventPolicyTable + v27 + 4);
  }
}

```

## disassembly

```asm
0x18000fc10  push    rbp
0x18000fc12  push    rbx
0x18000fc13  push    rdi
0x18000fc14  push    r12
0x18000fc16  mov     rbp, rsp
0x18000fc19  sub     rsp, 58h
0x18000fc1d  cmp     word ptr [rcx], 0
0x18000fc21  mov     r12, r8
0x18000fc24  mov     rdi, rdx
0x18000fc27  mov     rbx, rcx
0x18000fc2a  jz      short loc_18000FC5D
0x18000fc2c  cmp     qword ptr [rcx+8], 0
0x18000fc31  jnz     short loc_18000FC5D
0x18000fc33  xorps   xmm0, xmm0
0x18000fc36  mov     [rbp+var_10], 4
0x18000fc3d  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18000fc44  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18000fc4b  mov     [rbp+pExceptionObject], rax
0x18000fc4f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000fc53  movups  [rbp+var_20], xmm0
0x18000fc57  call    _CxxThrowException_0
0x18000fc5d  mov     [rsp+58h+arg_8], r13
0x18000fc65  xorps   xmm0, xmm0
0x18000fc68  movups  xmmword ptr [rdx], xmm0
0x18000fc6b  mov     [rsp+58h+arg_10], r14
0x18000fc73  xor     eax, eax
0x18000fc75  movups  xmmword ptr [rdx+10h], xmm0
0x18000fc79  mov     [rsp+58h+var_8], r15
0x18000fc7e  xor     r13b, r13b
0x18000fc81  movups  xmmword ptr [rdx+20h], xmm0
0x18000fc85  xor     r15b, r15b
0x18000fc88  mov     [rdx+30h], rax
0x18000fc8c  mov     [r8], rax
0x18000fc8f  xor     r14d, r14d
0x18000fc92  mov     [rsp+58h+arg_0], rsi
0x18000fc9a  movzx   eax, word ptr [rbx]
0x18000fc9d  lea     rcx, String2; "Type"
0x18000fca4  cmp     r14d, eax
0x18000fca7  jnb     loc_18001042F
0x18000fcad  mov     rax, [rbx+8]
0x18000fcb1  mov     esi, r14d
0x18000fcb4  shl     rsi, 5
0x18000fcb8  mov     r8, [rsi+rax]; lpString1
0x18000fcbc  test    r8, r8
0x18000fcbf  jz      loc_180010405
0x18000fcc5  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000fccd  mov     edx, 1; dwCmpFlags
0x18000fcd2  mov     [rsp+58h+lpString2], rcx; lpString2
0x18000fcd7  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000fcdd  mov     ecx, 7Fh; Locale
0x18000fce2  call    cs:__imp_CompareStringW
0x18000fce8  mov     r8, [rbx+8]
0x18000fcec  cmp     eax, 2
0x18000fcef  jnz     short loc_18000FD0A
0x18000fcf1  cmp     dword ptr [r8+rsi+8], 0
0x18000fcf7  jnz     loc_180010165
0x18000fcfd  mov     eax, [r8+rsi+10h]
0x18000fd02  inc     r14d
0x18000fd05  mov     [rdi+8], eax
0x18000fd08  jmp     short loc_18000FC9A
0x18000fd0a  mov     r8, [r8+rsi]; lpString1
0x18000fd0e  lea     rax, aTriggertype; "TriggerType"
0x18000fd15  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000fd1d  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000fd23  mov     edx, 1; dwCmpFlags
0x18000fd28  mov     [rsp+58h+lpString2], rax; lpString2
0x18000fd2d  mov     ecx, 7Fh; Locale
0x18000fd32  call    cs:__imp_CompareStringW
0x18000fd38  cmp     eax, 2
0x18000fd3b  jnz     short loc_18000FD5B
0x18000fd3d  mov     rax, [rbx+8]
0x18000fd41  cmp     dword ptr [rax+rsi+8], 0
0x18000fd46  jnz     loc_18001018F
0x18000fd4c  mov     eax, [rax+rsi+10h]
0x18000fd50  mov     r15b, 1
0x18000fd53  mov     [rdi+0Ch], eax
0x18000fd56  jmp     loc_18001015D
0x18000fd5b  mov     r8, [rbx+8]
0x18000fd5f  lea     rax, aEventname; "EventName"
0x18000fd66  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000fd6e  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000fd74  mov     edx, 1; dwCmpFlags
0x18000fd79  mov     [rsp+58h+lpString2], rax; lpString2
0x18000fd7e  mov     ecx, 7Fh; Locale
0x18000fd83  mov     r8, [r8+rsi]; lpString1
0x18000fd87  call    cs:__imp_CompareStringW
0x18000fd8d  cmp     eax, 2
0x18000fd90  jnz     short loc_18000FDAE
0x18000fd92  mov     rax, [rbx+8]
0x18000fd96  cmp     dword ptr [rax+rsi+8], 1
0x18000fd9b  jnz     loc_1800101B9
0x18000fda1  mov     rax, [rax+rsi+10h]
0x18000fda6  mov     [rdi], rax
0x18000fda9  jmp     loc_18001015D
0x18000fdae  mov     r8, [rbx+8]
0x18000fdb2  lea     rax, aOneshot; "OneShot"
0x18000fdb9  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000fdc1  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000fdc7  mov     edx, 1; dwCmpFlags
0x18000fdcc  mov     [rsp+58h+lpString2], rax; lpString2
0x18000fdd1  mov     ecx, 7Fh; Locale
0x18000fdd6  mov     r8, [r8+rsi]; lpString1
0x18000fdda  call    cs:__imp_CompareStringW
0x18000fde0  cmp     eax, 2
0x18000fde3  jnz     short loc_18000FE05
0x18000fde5  mov     rcx, [rbx+8]
0x18000fde9  cmp     dword ptr [rcx+rsi+8], 0
0x18000fdee  jnz     loc_1800101E3
0x18000fdf4  xor     eax, eax
0x18000fdf6  cmp     [rcx+rsi+10h], eax
0x18000fdfa  setnz   al
0x18000fdfd  mov     [rdi+18h], eax
0x18000fe00  jmp     loc_18001015D
0x18000fe05  mov     r8, [rbx+8]
0x18000fe09  lea     rax, aOperator; "Operator"
0x18000fe10  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000fe18  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000fe1e  mov     edx, 1; dwCmpFlags
0x18000fe23  mov     [rsp+58h+lpString2], rax; lpString2
0x18000fe28  mov     ecx, 7Fh; Locale
0x18000fe2d  mov     r8, [r8+rsi]; lpString1
0x18000fe31  call    cs:__imp_CompareStringW
0x18000fe37  cmp     eax, 2
0x18000fe3a  jnz     short loc_18000FE5A
0x18000fe3c  mov     rax, [rbx+8]
0x18000fe40  cmp     dword ptr [rax+rsi+8], 0
0x18000fe45  jnz     loc_18001020D
0x18000fe4b  mov     eax, [rax+rsi+10h]
0x18000fe4f  inc     r14d
0x18000fe52  mov     [rdi+10h], eax
0x18000fe55  jmp     loc_18000FC9A
0x18000fe5a  mov     r8, [rbx+8]
0x18000fe5e  lea     rax, aValue; "Value"
0x18000fe65  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000fe6d  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000fe73  mov     edx, 1; dwCmpFlags
0x18000fe78  mov     [rsp+58h+lpString2], rax; lpString2
0x18000fe7d  mov     ecx, 7Fh; Locale
0x18000fe82  mov     r8, [r8+rsi]; lpString1
0x18000fe86  call    cs:__imp_CompareStringW
0x18000fe8c  cmp     eax, 2
0x18000fe8f  jnz     short loc_18000FEAF
0x18000fe91  mov     rax, [rbx+8]
0x18000fe95  cmp     dword ptr [rax+rsi+8], 0
0x18000fe9a  jnz     loc_180010237
0x18000fea0  mov     eax, [rax+rsi+10h]
0x18000fea4  inc     r14d
0x18000fea7  mov     [rdi+14h], eax
0x18000feaa  jmp     loc_18000FC9A
0x18000feaf  mov     r8, [rbx+8]
0x18000feb3  lea     rax, aData; "Data"
0x18000feba  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000fec2  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000fec8  mov     edx, 1; dwCmpFlags
0x18000fecd  mov     [rsp+58h+lpString2], rax; lpString2
0x18000fed2  mov     ecx, 7Fh; Locale
0x18000fed7  mov     r8, [r8+rsi]; lpString1
0x18000fedb  call    cs:__imp_CompareStringW
0x18000fee1  cmp     eax, 2
0x18000fee4  jnz     short loc_18000FF51
0x18000fee6  mov     rax, [rbx+8]
0x18000feea  cmp     dword ptr [rax+rsi+8], 4
0x18000feef  jnz     loc_180010261
0x18000fef5  cmp     qword ptr [r12], 0
0x18000fefa  jnz     short loc_18000FF10
0x18000fefc  mov     ecx, 10h; Size
0x18000ff01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ff06  xorps   xmm0, xmm0
0x18000ff09  mov     [r12], rax
0x18000ff0d  movups  xmmword ptr [rax], xmm0
0x18000ff10  mov     rax, [rbx+8]
0x18000ff14  movzx   ecx, word ptr [rax+rsi+10h]
0x18000ff19  mov     rax, [r12]
0x18000ff1d  mov     [rax+8], ecx
0x18000ff20  mov     rax, [r12]
0x18000ff24  mov     ecx, [rax+8]; unsigned __int64
0x18000ff27  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ff2c  mov     rcx, [r12]
0x18000ff30  mov     [rcx], rax
0x18000ff33  mov     rcx, [r12]
0x18000ff37  mov     rdx, [rbx+8]
0x18000ff3b  mov     r8d, [rcx+8]; Size
0x18000ff3f  mov     rcx, [rcx]; void *
0x18000ff42  mov     rdx, [rdx+rsi+18h]; Src
0x18000ff47  call    memcpy_0
0x18000ff4c  jmp     loc_18001015D
0x18000ff51  mov     r8, [rbx+8]
0x18000ff55  lea     rax, aOffset; "Offset"
0x18000ff5c  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000ff64  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000ff6a  mov     edx, 1; dwCmpFlags
0x18000ff6f  mov     [rsp+58h+lpString2], rax; lpString2
0x18000ff74  mov     ecx, 7Fh; Locale
0x18000ff79  mov     r8, [r8+rsi]; lpString1
0x18000ff7d  call    cs:__imp_CompareStringW
0x18000ff83  cmp     eax, 2
0x18000ff86  jnz     short loc_18000FFC6
0x18000ff88  mov     rax, [rbx+8]
0x18000ff8c  cmp     dword ptr [rax+rsi+8], 0
0x18000ff91  jnz     loc_18001028B
0x18000ff97  cmp     qword ptr [r12], 0
0x18000ff9c  jnz     short loc_18000FFB2
0x18000ff9e  mov     ecx, 10h; Size
0x18000ffa3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ffa8  xorps   xmm0, xmm0
0x18000ffab  mov     [r12], rax
0x18000ffaf  movups  xmmword ptr [rax], xmm0
0x18000ffb2  mov     rax, [rbx+8]
0x18000ffb6  mov     rcx, [r12]
0x18000ffba  mov     eax, [rax+rsi+10h]
0x18000ffbe  mov     [rcx+0Ch], eax
0x18000ffc1  jmp     loc_18001015D
0x18000ffc6  test    r13b, r13b
0x18000ffc9  jnz     loc_1800103DB
0x18000ffcf  mov     r8, [rbx+8]
0x18000ffd3  lea     rax, aTriggeroptions; "TriggerOptions"
0x18000ffda  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000ffe2  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000ffe8  mov     edx, 1; dwCmpFlags
0x18000ffed  mov     [rsp+58h+lpString2], rax; lpString2
0x18000fff2  mov     ecx, 7Fh; Locale
0x18000fff7  mov     r8, [r8+rsi]; lpString1
0x18000fffb  call    cs:__imp_CompareStringW
0x180010001  cmp     eax, 2
0x180010004  jnz     loc_18001008C
0x18001000a  mov     rax, [rbx+8]
0x18001000e  cmp     dword ptr [rax+rsi+8], 4
0x180010013  jnz     loc_180010309
0x180010019  cmp     word ptr [rax+rsi+10h], 10h
0x18001001f  jnz     loc_1800102DF
0x180010025  mov     rcx, [rax+rsi+18h]
0x18001002a  mov     eax, [rcx]
0x18001002c  test    eax, eax
0x18001002e  jnz     short loc_180010035
0x180010030  mov     [rdi+1Ch], eax
0x180010033  jmp     short loc_180010061
0x180010035  cmp     eax, 1
0x180010038  jnz     short loc_180010043
0x18001003a  mov     dword ptr [rdi+1Ch], 20h ; ' '
0x180010041  jmp     short loc_180010061
0x180010043  cmp     eax, 2
0x180010046  jnz     short loc_180010051
0x180010048  mov     dword ptr [rdi+1Ch], 80h
0x18001004f  jmp     short loc_180010061
0x180010051  cmp     eax, 3
0x180010054  jnz     loc_1800102B5
0x18001005a  mov     dword ptr [rdi+1Ch], 8000h
0x180010061  cmp     byte ptr [rcx+4], 0
0x180010065  jz      short loc_18001006E
0x180010067  mov     dword ptr [rdi+20h], 1
0x18001006e  cmp     byte ptr [rcx+5], 0
0x180010072  jz      short loc_18001007B
0x180010074  mov     dword ptr [rdi+24h], 1
0x18001007b  mov     eax, [rcx+8]
0x18001007e  mov     [rdi+28h], eax
0x180010081  mov     eax, [rcx+0Ch]
0x180010084  mov     [rdi+2Ch], eax
0x180010087  jmp     loc_18001015A
0x18001008c  mov     r8, [rbx+8]
0x180010090  lea     rax, aCsebtriggeropt; "CSebTriggerOptions"
0x180010097  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001009f  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800100a5  mov     edx, 1; dwCmpFlags
0x1800100aa  mov     [rsp+58h+lpString2], rax; lpString2
0x1800100af  mov     ecx, 7Fh; Locale
0x1800100b4  mov     r8, [r8+rsi]; lpString1
0x1800100b8  call    cs:__imp_CompareStringW
0x1800100be  cmp     eax, 2
0x1800100c1  jnz     loc_1800103DB
0x1800100c7  mov     rax, [rbx+8]
0x1800100cb  cmp     dword ptr [rax+rsi+8], 4
0x1800100d0  jnz     loc_1800103B1
0x1800100d6  cmp     word ptr [rax+rsi+10h], 1Ch
0x1800100dc  jnz     loc_180010387
0x1800100e2  mov     rcx, [rax+rsi+18h]
0x1800100e7  cmp     dword ptr [rcx], 1
0x1800100ea  jnz     loc_18001035D
0x1800100f0  mov     eax, [rcx+4]
0x1800100f3  test    eax, eax
0x1800100f5  jnz     short loc_1800100FC
0x1800100f7  mov     [rdi+1Ch], eax
0x1800100fa  jmp     short loc_180010128
0x1800100fc  cmp     eax, 1
0x1800100ff  jnz     short loc_18001010A
0x180010101  mov     dword ptr [rdi+1Ch], 20h ; ' '
0x180010108  jmp     short loc_180010128
0x18001010a  cmp     eax, 2
0x18001010d  jnz     short loc_180010118
0x18001010f  mov     dword ptr [rdi+1Ch], 80h
0x180010116  jmp     short loc_180010128
0x180010118  cmp     eax, 3
0x18001011b  jnz     loc_180010333
0x180010121  mov     dword ptr [rdi+1Ch], 8000h
0x180010128  cmp     byte ptr [rcx+8], 0
0x18001012c  jz      short loc_180010135
0x18001012e  mov     dword ptr [rdi+20h], 1
0x180010135  cmp     byte ptr [rcx+9], 0
0x180010139  jz      short loc_180010142
0x18001013b  mov     dword ptr [rdi+24h], 1
0x180010142  mov     eax, [rcx+0Ch]
  ... truncated ...
```
