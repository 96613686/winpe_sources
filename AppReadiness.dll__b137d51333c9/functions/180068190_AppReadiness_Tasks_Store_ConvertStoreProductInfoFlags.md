# AppReadiness::Tasks::Store::ConvertStoreProductInfoFlags

- ea: `0x180068190`
- end: `0x18006828f`
- name: `AppReadiness::Tasks::Store::ConvertStoreProductInfoFlags`
- size: `255`
- prototype: `__int64 __fastcall(LPCWCH lpString2, LPCWCH lpString1)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180068190`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800681d7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800681fd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068224`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006824a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068271`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800681d7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800681fd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068224`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006824a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180068271`

## pseudocode

```c
int __fastcall AppReadiness::Tasks::Store::ConvertStoreProductInfoFlags(
        LPCWCH lpString2,
        const WCHAR *lpString1,
        _DWORD *a3)
{
  const WCHAR *v4; // rax

  v4 = lpString1;
  if ( *((_QWORD *)lpString1 + 2) )
  {
    if ( *((_QWORD *)lpString1 + 3) > 7u )
      v4 = *(const WCHAR **)lpString1;
    LODWORD(v4) = CompareStringOrdinal(v4, -1, L"true", -1, 1);
    if ( (_DWORD)v4 == 2 )
    {
      LODWORD(v4) = CompareStringOrdinal(L"Appl", -1, lpString2, -1, 0);
      if ( (_DWORD)v4 == 2 )
      {
        *a3 |= 1u;
      }
      else
      {
        LODWORD(v4) = CompareStringOrdinal(L"Inst", -1, lpString2, -1, 0);
        if ( (_DWORD)v4 == 2 )
        {
          *a3 |= 2u;
        }
        else
        {
          LODWORD(v4) = CompareStringOrdinal(L"HasUpd", -1, lpString2, -1, 0);
          if ( (_DWORD)v4 == 2 )
          {
            *a3 |= 4u;
          }
          else
          {
            LODWORD(v4) = CompareStringOrdinal(L"Dca", -1, lpString2, -1, 0);
            if ( (_DWORD)v4 == 2 )
              *a3 |= 8u;
          }
        }
      }
    }
  }
  return (int)v4;
}

```

## disassembly

```asm
0x180068190  mov     [rsp+arg_0], rbx
0x180068195  mov     [rsp+arg_8], rsi
0x18006819a  push    rdi
0x18006819b  sub     rsp, 30h
0x18006819f  cmp     qword ptr [rdx+10h], 0
0x1800681a4  mov     rbx, r8
0x1800681a7  mov     rax, rdx
0x1800681aa  mov     rdi, rcx
0x1800681ad  jz      loc_18006827F
0x1800681b3  cmp     qword ptr [rdx+18h], 7
0x1800681b8  jbe     short loc_1800681BD
0x1800681ba  mov     rax, [rdx]
0x1800681bd  or      esi, 0FFFFFFFFh
0x1800681c0  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800681c8  mov     r9d, esi; cchCount2
0x1800681cb  lea     r8, String2; "true"
0x1800681d2  mov     edx, esi; cchCount1
0x1800681d4  mov     rcx, rax; lpString1
0x1800681d7  call    cs:__imp_CompareStringOrdinal
0x1800681dd  cmp     eax, 2
0x1800681e0  jnz     loc_18006827F
0x1800681e6  mov     r9d, esi; cchCount2
0x1800681e9  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x1800681f1  mov     r8, rdi; lpString2
0x1800681f4  lea     rcx, aAppl; "Appl"
0x1800681fb  mov     edx, esi; cchCount1
0x1800681fd  call    cs:__imp_CompareStringOrdinal
0x180068203  cmp     eax, 2
0x180068206  jnz     short loc_18006820D
0x180068208  or      dword ptr [rbx], 1
0x18006820b  jmp     short loc_18006827F
0x18006820d  mov     r9d, esi; cchCount2
0x180068210  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x180068218  mov     r8, rdi; lpString2
0x18006821b  lea     rcx, aInst; "Inst"
0x180068222  mov     edx, esi; cchCount1
0x180068224  call    cs:__imp_CompareStringOrdinal
0x18006822a  cmp     eax, 2
0x18006822d  jnz     short loc_180068233
0x18006822f  or      [rbx], eax
0x180068231  jmp     short loc_18006827F
0x180068233  mov     r9d, esi; cchCount2
0x180068236  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x18006823e  mov     r8, rdi; lpString2
0x180068241  lea     rcx, aHasupd; "HasUpd"
0x180068248  mov     edx, esi; cchCount1
0x18006824a  call    cs:__imp_CompareStringOrdinal
0x180068250  cmp     eax, 2
0x180068253  jnz     short loc_18006825A
0x180068255  or      dword ptr [rbx], 4
0x180068258  jmp     short loc_18006827F
0x18006825a  mov     r9d, esi; cchCount2
0x18006825d  mov     [rsp+38h+bIgnoreCase], 0; bIgnoreCase
0x180068265  mov     r8, rdi; lpString2
0x180068268  lea     rcx, aDca; "Dca"
0x18006826f  mov     edx, esi; cchCount1
0x180068271  call    cs:__imp_CompareStringOrdinal
0x180068277  cmp     eax, 2
0x18006827a  jnz     short loc_18006827F
0x18006827c  or      dword ptr [rbx], 8
0x18006827f  mov     rbx, [rsp+38h+arg_0]
0x180068284  mov     rsi, [rsp+38h+arg_8]
0x180068289  add     rsp, 30h
0x18006828d  pop     rdi
0x18006828e  retn
```
