# ServiceUpCall

- ea: `0x1400072b8`
- end: `0x1400074f2`
- name: `ServiceUpCall`
- size: `570`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64, DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140007500`

## callees

- `0x1400072b8`
- `0x140010234`
- `0x1400104fc`
- `0x140010a1c`
- `0x14001830e`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x14000746f`
- `KERNEL32!GetComputerNameW` at `0x14000746f`
- `KERNEL32!GetLastError` at `0x14000748b`
- `KERNEL32!GetLastError` at `0x14000748b`
- `KERNEL32!GetComputerNameA` at `0x14000744f`
- `KERNEL32!GetComputerNameA` at `0x14000744f`

## pseudocode

```c
__int64 __fastcall ServiceUpCall(__int64 a1, unsigned int a2, __int64 a3, __int64 a4, DWORD *a5)
{
  _DWORD *v8; // r14
  int v9; // edi
  int v10; // r9d
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  bool v18; // zf
  int v19; // eax
  DWORD v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  WCHAR *v27; // rcx
  DWORD *v28; // rax
  DWORD nSize; // [rsp+68h] [rbp+20h] BYREF

  v18 = NfsClntGlobals == 0;
  nSize = 0;
  *(_QWORD *)a3 = *(_QWORD *)a1;
  *(_DWORD *)(a3 + 8) = *(_DWORD *)(a1 + 8);
  if ( v18 )
  {
    *(_QWORD *)(a3 + 24) = 0;
    v8 = (_DWORD *)(a3 + 40);
    v9 = -1073741822;
    *(_DWORD *)(a3 + 16) = -1073741822;
    *(_DWORD *)(a3 + 32) = 0;
    memset_0((void *)(a3 + 40), 0, 0x7D8u);
    v11 = *(_DWORD *)(a1 + 8);
    if ( v11 > 8 )
    {
      v21 = v11 - 9;
      if ( !v21 )
        goto LABEL_37;
      v22 = v21 - 1;
      if ( !v22 )
        goto LABEL_37;
      v23 = v22 - 1;
      if ( !v23 )
        goto LABEL_37;
      v24 = v23 - 1;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( !v25 )
          goto LABEL_37;
        v26 = v25 - 2;
        if ( !v26 )
        {
          if ( a2 >= 0x10 )
          {
            *v8 = 56;
            nSize = 129;
            *(_DWORD *)(a3 + 48) = 188;
            if ( GetComputerNameA((LPSTR)(a3 + 56), &nSize)
              && (v27 = (WCHAR *)(a3 + *(unsigned int *)(a3 + 48)),
                  *(_DWORD *)(a3 + 44) = nSize,
                  nSize = 129,
                  GetComputerNameW(v27, &nSize)) )
            {
              v9 = 0;
              *(_DWORD *)(a3 + 52) = 2 * nSize;
            }
            else
            {
              v9 = -1073741823;
              *(_DWORD *)(a3 + 32) = GetLastError();
            }
          }
          else
          {
            v9 = -2147483643;
          }
          v20 = 448;
          goto LABEL_41;
        }
        v18 = v26 == 7;
LABEL_26:
        if ( !v18 )
        {
          v9 = -1073741811;
LABEL_40:
          v20 = 40;
LABEL_41:
          v28 = a5;
          *(_DWORD *)(a3 + 16) = v9;
          *v28 = v20;
          *(_QWORD *)(a3 + 24) = v20;
          return 0;
        }
LABEL_37:
        v20 = nSize;
        if ( nSize > 0x800 )
          v20 = 2048;
        if ( v20 > 0x28 )
          goto LABEL_41;
        goto LABEL_40;
      }
      v19 = NfsUpCallDispatchGetUidGidWithPasswdGroupClient(0, a1, a2, a3);
    }
    else if ( v11 == 8 )
    {
      v19 = NfsUpCallDispatchGetUidGidWithLdapClient(a1, a2, a3, v10, (__int64)&nSize);
    }
    else
    {
      if ( !v11 )
      {
        if ( a2 >= 0x14 )
        {
          v9 = 0;
          *v8 = *(_DWORD *)(a1 + 16) + 1;
        }
        else
        {
          v9 = -2147483643;
        }
        v20 = 44;
        goto LABEL_41;
      }
      v12 = v11 - 1;
      if ( !v12 )
        goto LABEL_37;
      v13 = v12 - 1;
      if ( !v13 )
        goto LABEL_37;
      v14 = v13 - 1;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( !v15 )
          goto LABEL_37;
        v16 = v15 - 1;
        if ( !v16 )
          goto LABEL_37;
        v17 = v16 - 1;
        if ( !v17 )
          goto LABEL_37;
        v18 = v17 == 1;
        goto LABEL_26;
      }
      v19 = NfsUpCallDispatchGetHostAddressListByName(a1, a2, a3, v10, (__int64)&nSize);
    }
    v9 = v19;
    goto LABEL_37;
  }
  *(_DWORD *)(a3 + 16) = -1073741536;
  *(_QWORD *)(a3 + 24) = 40;
  *(_DWORD *)(a3 + 32) = 0;
  return 0;
}

```

## disassembly

```asm
0x1400072b8  mov     rax, rsp
0x1400072bb  mov     [rax+8], rbx
0x1400072bf  mov     [rax+10h], rbp
0x1400072c3  mov     [rax+20h], r9d
0x1400072c7  push    rsi
0x1400072c8  push    rdi
0x1400072c9  push    r14
0x1400072cb  sub     rsp, 30h
0x1400072cf  cmp     cs:NfsClntGlobals, 0
0x1400072d6  mov     rbx, r8
0x1400072d9  mov     dword ptr [rax+20h], 0
0x1400072e0  mov     ebp, edx
0x1400072e2  mov     rax, [rcx]
0x1400072e5  mov     rsi, rcx
0x1400072e8  mov     [r8], rax
0x1400072eb  mov     eax, [rcx+8]
0x1400072ee  mov     [r8+8], eax
0x1400072f2  jz      short loc_14000730F
0x1400072f4  xor     eax, eax
0x1400072f6  mov     dword ptr [r8+10h], 0C0000120h
0x1400072fe  mov     qword ptr [r8+18h], 28h ; '('
0x140007306  mov     [r8+20h], eax
0x14000730a  jmp     loc_1400074DD
0x14000730f  mov     qword ptr [r8+18h], 0
0x140007317  lea     r14, [r8+28h]
0x14000731b  xor     eax, eax
0x14000731d  mov     edi, 0C0000002h
0x140007322  mov     [r8+10h], edi
0x140007326  xor     edx, edx; Val
0x140007328  mov     [r8+20h], eax
0x14000732c  mov     rcx, r14; void *
0x14000732f  mov     r8d, 7D8h; Size
0x140007335  call    memset_0
0x14000733a  mov     ecx, [rsi+8]
0x14000733d  cmp     ecx, 8
0x140007340  jg      loc_1400073DE
0x140007346  jz      short loc_1400073C2
0x140007348  test    ecx, ecx
0x14000734a  jz      short loc_1400073A2
0x14000734c  sub     ecx, 1
0x14000734f  jz      loc_1400074B5
0x140007355  sub     ecx, 1
0x140007358  jz      loc_1400074B5
0x14000735e  sub     ecx, 1
0x140007361  jz      short loc_140007386
0x140007363  sub     ecx, 1
0x140007366  jz      loc_1400074B5
0x14000736c  sub     ecx, 1
0x14000736f  jz      loc_1400074B5
0x140007375  sub     ecx, 1
0x140007378  jz      loc_1400074B5
0x14000737e  cmp     ecx, 1
0x140007381  jmp     loc_140007413
0x140007386  lea     rax, [rsp+48h+nSize]
0x14000738b  mov     r8, rbx
0x14000738e  mov     edx, ebp
0x140007390  mov     [rsp+48h+var_28], rax
0x140007395  mov     rcx, rsi
0x140007398  call    NfsUpCallDispatchGetHostAddressListByName
0x14000739d  jmp     loc_1400074B3
0x1400073a2  cmp     ebp, 14h
0x1400073a5  jnb     short loc_1400073AE
0x1400073a7  mov     edi, 80000005h
0x1400073ac  jmp     short loc_1400073B8
0x1400073ae  mov     eax, [rsi+10h]
0x1400073b1  xor     edi, edi
0x1400073b3  inc     eax
0x1400073b5  mov     [r14], eax
0x1400073b8  mov     ecx, 2Ch ; ','
0x1400073bd  jmp     loc_1400074CD
0x1400073c2  lea     rax, [rsp+48h+nSize]
0x1400073c7  mov     r8, rbx
0x1400073ca  mov     edx, ebp
0x1400073cc  mov     [rsp+48h+var_28], rax
0x1400073d1  mov     rcx, rsi
0x1400073d4  call    NfsUpCallDispatchGetUidGidWithLdapClient
0x1400073d9  jmp     loc_1400074B3
0x1400073de  sub     ecx, 9
0x1400073e1  jz      loc_1400074B5
0x1400073e7  sub     ecx, 1
0x1400073ea  jz      loc_1400074B5
0x1400073f0  sub     ecx, 1
0x1400073f3  jz      loc_1400074B5
0x1400073f9  sub     ecx, 1
0x1400073fc  jz      loc_14000749B
0x140007402  sub     ecx, 1
0x140007405  jz      loc_1400074B5
0x14000740b  sub     ecx, 2
0x14000740e  jz      short loc_140007423
0x140007410  cmp     ecx, 7
0x140007413  jz      loc_1400074B5
0x140007419  mov     edi, 0C000000Dh
0x14000741e  jmp     loc_1400074C8
0x140007423  cmp     ebp, 10h
0x140007426  jnb     short loc_14000742F
0x140007428  mov     edi, 80000005h
0x14000742d  jmp     short loc_140007494
0x14000742f  mov     edi, 81h
0x140007434  mov     dword ptr [r14], 38h ; '8'
0x14000743b  lea     rcx, [rbx+38h]; lpBuffer
0x14000743f  mov     [rsp+48h+nSize], edi
0x140007443  lea     rdx, [rsp+48h+nSize]; nSize
0x140007448  mov     dword ptr [rbx+30h], 0BCh
0x14000744f  call    cs:__imp_GetComputerNameA
0x140007455  test    eax, eax
0x140007457  jz      short loc_140007486
0x140007459  mov     eax, [rsp+48h+nSize]
0x14000745d  lea     rdx, [rsp+48h+nSize]; nSize
0x140007462  mov     ecx, [rbx+30h]
0x140007465  add     rcx, rbx; lpBuffer
0x140007468  mov     [rbx+2Ch], eax
0x14000746b  mov     [rsp+48h+nSize], edi
0x14000746f  call    cs:__imp_GetComputerNameW
0x140007475  test    eax, eax
0x140007477  jz      short loc_140007486
0x140007479  mov     eax, [rsp+48h+nSize]
0x14000747d  xor     edi, edi
0x14000747f  add     eax, eax
0x140007481  mov     [rbx+34h], eax
0x140007484  jmp     short loc_140007494
0x140007486  mov     edi, 0C0000001h
0x14000748b  call    cs:__imp_GetLastError
0x140007491  mov     [rbx+20h], eax
0x140007494  mov     ecx, 1C0h
0x140007499  jmp     short loc_1400074CD
0x14000749b  lea     rax, [rsp+48h+nSize]
0x1400074a0  mov     r9, rbx
0x1400074a3  mov     r8d, ebp
0x1400074a6  mov     [rsp+48h+var_20], rax
0x1400074ab  mov     rdx, rsi
0x1400074ae  call    NfsUpCallDispatchGetUidGidWithPasswdGroupClient
0x1400074b3  mov     edi, eax
0x1400074b5  mov     ecx, [rsp+48h+nSize]
0x1400074b9  mov     eax, 800h
0x1400074be  cmp     ecx, eax
0x1400074c0  cmova   ecx, eax
0x1400074c3  cmp     ecx, 28h ; '('
0x1400074c6  ja      short loc_1400074CD
0x1400074c8  mov     ecx, 28h ; '('
0x1400074cd  mov     rax, [rsp+48h+arg_20]
0x1400074d2  mov     [rbx+10h], edi
0x1400074d5  mov     [rax], ecx
0x1400074d7  mov     eax, ecx
0x1400074d9  mov     [rbx+18h], rax
0x1400074dd  mov     rbx, [rsp+48h+arg_0]
0x1400074e2  xor     eax, eax
0x1400074e4  mov     rbp, [rsp+48h+arg_8]
0x1400074e9  add     rsp, 30h
0x1400074ed  pop     r14
0x1400074ef  pop     rdi
0x1400074f0  pop     rsi
0x1400074f1  retn
```
