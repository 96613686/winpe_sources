# GetAppmgmtIniFilePath(void *,ushort * *)

- ea: `0x1800290cc`
- end: `0x18002931e`
- name: `?GetAppmgmtIniFilePath@@YAJPEAXPEAPEAG@Z`
- size: `594`
- prototype: `signed int __fastcall(PSID Sid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180029324`

## callees

- `0x1800016d0`
- `0x180002aa0`
- `0x18000cc10`
- `0x1800290cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029168`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029139`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800291d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800292e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800292ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029139`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800291d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800292e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800292ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029149`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029219`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029149`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029219`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002915c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002915c`
- `ntdll!RtlFreeUnicodeString` at `0x1800292d1`
- `ntdll!RtlFreeUnicodeString` at `0x180029309`
- `ntdll!RtlFreeUnicodeString` at `0x1800292d1`
- `ntdll!RtlFreeUnicodeString` at `0x180029309`
- `ntdll!RtlNtStatusToDosError` at `0x1800291dc`
- `ntdll!RtlNtStatusToDosError` at `0x1800291dc`
- `ntdll!RtlInitUnicodeString` at `0x1800291eb`
- `ntdll!RtlInitUnicodeString` at `0x1800291eb`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800291bb`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800291bb`

## pseudocode

```c
signed int __fastcall GetAppmgmtIniFilePath(PSID Sid, unsigned __int16 **a2)
{
  _BYTE *v2; // rbx
  WCHAR *v4; // rcx
  UINT v6; // esi
  _BYTE *v7; // rax
  UINT SystemDirectoryW; // edi
  signed int result; // eax
  int v10; // esi
  __int64 v11; // r14
  unsigned __int64 v12; // r15
  SIZE_T v13; // rax
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  int v16; // edi
  unsigned int v17; // r11d
  unsigned __int16 *v18; // rcx
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE hMem[528]; // [rsp+30h] [rbp-D0h] BYREF

  v2 = hMem;
  UnicodeString = 0;
  *a2 = 0;
  v4 = (WCHAR *)hMem;
  v6 = 260;
  while ( 1 )
  {
    SystemDirectoryW = GetSystemDirectoryW(v4, v6);
    if ( !SystemDirectoryW )
      break;
    if ( SystemDirectoryW < v6 )
    {
      if ( Sid )
      {
        v10 = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
        if ( v10 < 0 )
        {
          if ( v2 != hMem )
            LocalFree(v2);
          result = RtlNtStatusToDosError(v10);
          goto LABEL_9;
        }
      }
      else
      {
        RtlInitUnicodeString(&UnicodeString, L"MACHINE");
      }
      v11 = -1;
      v12 = SystemDirectoryW + (UnicodeString.Length >> 1) + 24;
      v13 = 2 * v12;
      if ( !is_mul_ok(v12, 2u) )
        v13 = -1;
      v14 = (unsigned __int16 *)LocalAlloc(0, v13);
      v15 = v14;
      if ( v14 )
      {
        v16 = StringCchCopyW(v14, (unsigned int)v12, (const unsigned __int16 *)v2);
        if ( v16 >= 0 )
        {
          if ( v2 )
          {
            do
              ++v11;
            while ( *(_WORD *)&v2[2 * v11] != (_WORD)v17 );
          }
          else
          {
            v11 = v17;
          }
          if ( *(_WORD *)&v2[2 * v11 - 2] == 92 || (v16 = StringCchCatW(v15, v12, L"\\"), v16 >= 0) )
          {
            v16 = StringCchCatW(v15, v12, L"appmgmt\\");
            if ( v16 >= 0 )
            {
              v16 = StringCchCatW(v15, v12, UnicodeString.Buffer);
              if ( v16 >= 0 )
              {
                v16 = StringCchCatW(v15, v12, L"\\AppMgmt.ini");
                if ( v16 >= 0 )
                {
                  *a2 = v15;
                  goto LABEL_40;
                }
              }
            }
          }
        }
        if ( Sid )
          RtlFreeUnicodeString(&UnicodeString);
        if ( v2 != hMem )
          LocalFree(v2);
        v18 = v15;
LABEL_37:
        LocalFree(v18);
      }
      else
      {
        v16 = -2147024882;
LABEL_40:
        if ( Sid )
          RtlFreeUnicodeString(&UnicodeString);
        if ( v2 != hMem )
        {
          v18 = (unsigned __int16 *)v2;
          goto LABEL_37;
        }
      }
      return v16;
    }
    v6 = SystemDirectoryW + 1;
    if ( v2 != hMem )
      LocalFree(v2);
    v7 = LocalAlloc(0x40u, 2LL * v6);
    v2 = v7;
    if ( !v7 )
      return -2147024882;
    v4 = (WCHAR *)v7;
  }
  result = GetLastError();
LABEL_9:
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800290cc  mov     [rsp-8+arg_10], rbx
0x1800290d1  push    rbp
0x1800290d2  push    rsi
0x1800290d3  push    rdi
0x1800290d4  push    r12
0x1800290d6  push    r13
0x1800290d8  push    r14
0x1800290da  push    r15
0x1800290dc  lea     rbp, [rsp-150h]
0x1800290e4  sub     rsp, 250h
0x1800290eb  mov     rax, cs:__security_cookie
0x1800290f2  xor     rax, rsp
0x1800290f5  mov     [rbp+180h+var_40], rax
0x1800290fc  xorps   xmm0, xmm0
0x1800290ff  lea     rbx, [rsp+280h+hMem]
0x180029104  xor     r14d, r14d
0x180029107  mov     r12, rcx
0x18002910a  movups  xmmword ptr [rsp+280h+UnicodeString.Length], xmm0
0x18002910f  mov     [rdx], r14
0x180029112  lea     rcx, [rsp+280h+hMem]
0x180029117  mov     r13, rdx
0x18002911a  mov     esi, 104h
0x18002911f  jmp     short loc_18002915A
0x180029121  cmp     edi, esi
0x180029123  jb      loc_1800291AB
0x180029129  lea     rax, [rsp+280h+hMem]
0x18002912e  lea     esi, [rdi+1]
0x180029131  cmp     rbx, rax
0x180029134  jz      short loc_18002913F
0x180029136  mov     rcx, rbx; hMem
0x180029139  call    cs:__imp_LocalFree
0x18002913f  mov     edx, esi
0x180029141  mov     ecx, 40h ; '@'; uFlags
0x180029146  add     rdx, rdx; uBytes
0x180029149  call    cs:__imp_LocalAlloc
0x18002914f  mov     rbx, rax
0x180029152  test    rax, rax
0x180029155  jz      short loc_1800291A4
0x180029157  mov     rcx, rax; lpBuffer
0x18002915a  mov     edx, esi; uSize
0x18002915c  call    cs:__imp_GetSystemDirectoryW
0x180029162  mov     edi, eax
0x180029164  test    eax, eax
0x180029166  jnz     short loc_180029121
0x180029168  call    cs:__imp_GetLastError
0x18002916e  test    eax, eax
0x180029170  jle     short loc_18002917A
0x180029172  movzx   eax, ax
0x180029175  or      eax, 80070000h
0x18002917a  mov     rcx, [rbp+180h+var_40]
0x180029181  xor     rcx, rsp; StackCookie
0x180029184  call    __security_check_cookie
0x180029189  mov     rbx, [rsp+280h+arg_10]
0x180029191  add     rsp, 250h
0x180029198  pop     r15
0x18002919a  pop     r14
0x18002919c  pop     r13
0x18002919e  pop     r12
0x1800291a0  pop     rdi
0x1800291a1  pop     rsi
0x1800291a2  pop     rbp
0x1800291a3  retn
0x1800291a4  mov     eax, 8007000Eh
0x1800291a9  jmp     short loc_18002917A
0x1800291ab  lea     rcx, [rsp+280h+UnicodeString]; DestinationString
0x1800291b0  test    r12, r12
0x1800291b3  jz      short loc_1800291E4
0x1800291b5  mov     r8b, 1; AllocateDestinationString
0x1800291b8  mov     rdx, r12; Sid
0x1800291bb  call    cs:__imp_RtlConvertSidToUnicodeString
0x1800291c1  mov     esi, eax
0x1800291c3  test    eax, eax
0x1800291c5  jns     short loc_1800291F1
0x1800291c7  lea     rax, [rsp+280h+hMem]
0x1800291cc  cmp     rbx, rax
0x1800291cf  jz      short loc_1800291DA
0x1800291d1  mov     rcx, rbx; hMem
0x1800291d4  call    cs:__imp_LocalFree
0x1800291da  mov     ecx, esi; Status
0x1800291dc  call    cs:__imp_RtlNtStatusToDosError
0x1800291e2  jmp     short loc_18002916E
0x1800291e4  lea     rdx, SourceString; "MACHINE"
0x1800291eb  call    cs:__imp_RtlInitUnicodeString
0x1800291f1  movzx   r15d, [rsp+280h+UnicodeString.Length]
0x1800291f7  mov     eax, 2
0x1800291fc  shr     r15d, 1
0x1800291ff  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180029206  add     r15d, 18h
0x18002920a  add     r15d, edi
0x18002920d  mul     r15
0x180029210  cmovb   rax, r14
0x180029214  xor     ecx, ecx; uFlags
0x180029216  mov     rdx, rax; uBytes
0x180029219  call    cs:__imp_LocalAlloc
0x18002921f  xor     r11d, r11d
0x180029222  mov     rsi, rax
0x180029225  test    rax, rax
0x180029228  jz      loc_1800292FA
0x18002922e  mov     r8, rbx; unsigned __int16 *
0x180029231  mov     edx, r15d; unsigned __int64
0x180029234  mov     rcx, rax; unsigned __int16 *
0x180029237  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002923c  mov     edi, eax
0x18002923e  test    eax, eax
0x180029240  js      loc_1800292C7
0x180029246  test    rbx, rbx
0x180029249  jnz     short loc_180029250
0x18002924b  mov     r14d, r11d
0x18002924e  jmp     short loc_18002925A
0x180029250  inc     r14
0x180029253  cmp     [rbx+r14*2], r11w
0x180029258  jnz     short loc_180029250
0x18002925a  cmp     word ptr [rbx+r14*2-2], 5Ch ; '\'
0x180029261  jz      short loc_18002927B
0x180029263  lea     r8, asc_18002EE30; "\\"
0x18002926a  mov     rdx, r15; unsigned __int64
0x18002926d  mov     rcx, rsi; unsigned __int16 *
0x180029270  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180029275  mov     edi, eax
0x180029277  test    eax, eax
0x180029279  js      short loc_1800292C7
0x18002927b  lea     r8, aAppmgmt_1; "appmgmt\\"
0x180029282  mov     rdx, r15; unsigned __int64
0x180029285  mov     rcx, rsi; unsigned __int16 *
0x180029288  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002928d  mov     edi, eax
0x18002928f  test    eax, eax
0x180029291  js      short loc_1800292C7
0x180029293  mov     r8, [rsp+280h+UnicodeString.Buffer]; unsigned __int16 *
0x180029298  mov     rdx, r15; unsigned __int64
0x18002929b  mov     rcx, rsi; unsigned __int16 *
0x18002929e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800292a3  mov     edi, eax
0x1800292a5  test    eax, eax
0x1800292a7  js      short loc_1800292C7
0x1800292a9  lea     r8, aAppmgmtIni; "\\AppMgmt.ini"
0x1800292b0  mov     rdx, r15; unsigned __int64
0x1800292b3  mov     rcx, rsi; unsigned __int16 *
0x1800292b6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800292bb  mov     edi, eax
0x1800292bd  test    eax, eax
0x1800292bf  js      short loc_1800292C7
0x1800292c1  mov     [r13+0], rsi
0x1800292c5  jmp     short loc_1800292FF
0x1800292c7  test    r12, r12
0x1800292ca  jz      short loc_1800292D7
0x1800292cc  lea     rcx, [rsp+280h+UnicodeString]; UnicodeString
0x1800292d1  call    cs:__imp_RtlFreeUnicodeString
0x1800292d7  lea     rax, [rsp+280h+hMem]
0x1800292dc  cmp     rbx, rax
0x1800292df  jz      short loc_1800292EA
0x1800292e1  mov     rcx, rbx; hMem
0x1800292e4  call    cs:__imp_LocalFree
0x1800292ea  mov     rcx, rsi; hMem
0x1800292ed  call    cs:__imp_LocalFree
0x1800292f3  mov     eax, edi
0x1800292f5  jmp     loc_18002917A
0x1800292fa  mov     edi, 8007000Eh
0x1800292ff  test    r12, r12
0x180029302  jz      short loc_18002930F
0x180029304  lea     rcx, [rsp+280h+UnicodeString]; UnicodeString
0x180029309  call    cs:__imp_RtlFreeUnicodeString
0x18002930f  lea     rax, [rsp+280h+hMem]
0x180029314  cmp     rbx, rax
0x180029317  jz      short loc_1800292F3
0x180029319  mov     rcx, rbx
0x18002931c  jmp     short loc_1800292ED
```
