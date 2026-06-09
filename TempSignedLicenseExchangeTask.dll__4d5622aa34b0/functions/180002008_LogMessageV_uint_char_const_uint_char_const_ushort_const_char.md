# LogMessageV(uint,char const *,uint,char const *,ushort const *,char *)

- ea: `0x180002008`
- end: `0x1800021fe`
- name: `?LogMessageV@@YAXIPEBDI0PEBGPEAD@Z`
- size: `502`
- prototype: `void __fastcall(int, const char *, __int64, const char *, wchar_t *Format, va_list Args)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180001fd8`

## callees

- `0x180001400`
- `0x180001f78`
- `0x180001fd8`
- `0x180002008`
- `0x180002204`
- `0x18000ca50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800021d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800021d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002049`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800020a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800020a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800021cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800020ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800020ca`

## string_xrefs

- `0x180002195`: `onecoreuap\enduser\winstore\licensemanager\tslexchangetask\logging.cpp`

## pseudocode

```c
void __fastcall LogMessageV(int a1, const char *a2, __int64 a3, const char *a4, wchar_t *Format, va_list Args)
{
  DWORD LastError; // r14d
  unsigned int v9; // eax
  unsigned __int16 *v10; // rbx
  unsigned __int64 v11; // rsi
  signed int v12; // ecx
  unsigned __int64 v13; // rdi
  int v14; // eax
  wchar_t Buffer[2047]; // [rsp+50h] [rbp-1058h] BYREF
  __int16 v16; // [rsp+104Eh] [rbp-5Ah]

  LastError = GetLastError();
  v9 = vsnwprintf(Buffer, 0x7FFu, Format, Args);
  if ( v9 < 0x800 )
  {
    v10 = Buffer;
    if ( v9 == 2047 )
      v16 = 0;
LABEL_19:
    if ( (unsigned __int16)a1 != 1 && (unsigned int)(unsigned __int16)a1 - 2 >= 2 )
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\tslexchangetask\\logging.cpp",
        0x55u,
        "LogMessageV",
        (wchar_t *)L"Assert (%s): %s",
        L"0",
        L"Failed");
    LogSimpleMessage(a1, v10, a4);
    goto LABEL_23;
  }
  v11 = 2048;
  v16 = 0;
  v10 = 0;
  do
  {
    v11 *= 2LL;
    LocalFree(v10);
    if ( is_mul_ok(v11, 2u) )
    {
      v10 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v11);
      v12 = v10 == 0 ? 0x8007000E : 0;
      if ( v10 )
      {
        if ( v11 )
        {
          if ( v11 <= 0x7FFFFFFF )
          {
            v13 = v11 - 1;
            v14 = vsnwprintf(v10, v11 - 1, Format, Args);
            if ( v14 < 0 || v14 > v13 )
            {
              v12 = -2147024774;
              v10[v13] = 0;
            }
            else
            {
              v12 = 0;
              if ( v14 == v13 )
                v10[v13] = 0;
            }
          }
          else
          {
            v12 = -2147024809;
            *v10 = 0;
          }
        }
        else
        {
          v12 = -2147024809;
        }
      }
    }
    else
    {
      v10 = 0;
      v12 = -2147024362;
    }
  }
  while ( v12 == -2147024774 );
  if ( v12 >= 0 )
    goto LABEL_19;
LABEL_23:
  if ( v10 != Buffer )
    LocalFree(v10);
  SetLastError(LastError);
}

```

## disassembly

```asm
0x180002008  push    rbx
0x18000200a  push    rbp
0x18000200b  push    rsi
0x18000200c  push    rdi
0x18000200d  push    r12
0x18000200f  push    r13
0x180002011  push    r14
0x180002013  push    r15
0x180002015  mov     eax, 1068h
0x18000201a  call    _alloca_probe
0x18000201f  sub     rsp, rax
0x180002022  mov     rax, cs:__security_cookie
0x180002029  xor     rax, rsp
0x18000202c  mov     [rsp+10A8h+var_58], rax
0x180002034  mov     r15, [rsp+10A8h+Format]
0x18000203c  mov     r13, r9
0x18000203f  mov     r12, [rsp+10A8h+Args]
0x180002047  mov     ebp, ecx
0x180002049  call    cs:__imp_GetLastError
0x18000204f  mov     edi, 7FFh
0x180002054  lea     rcx, [rsp+10A8h+Buffer]; Buffer
0x180002059  mov     edx, edi; BufferCount
0x18000205b  mov     r9, r12; Args
0x18000205e  mov     r8, r15; Format
0x180002061  mov     r14d, eax
0x180002064  call    _vsnwprintf
0x180002069  test    eax, eax
0x18000206b  js      short loc_18000208B
0x18000206d  cmp     eax, edi
0x18000206f  ja      short loc_18000208B
0x180002071  lea     rbx, [rsp+10A8h+Buffer]
0x180002076  jnz     loc_18000215E
0x18000207c  xor     eax, eax
0x18000207e  mov     [rsp+10A8h+var_5A], ax
0x180002086  jmp     loc_18000215E
0x18000208b  xor     eax, eax
0x18000208d  mov     esi, 800h
0x180002092  mov     [rsp+10A8h+var_5A], ax
0x18000209a  xor     ebx, ebx
0x18000209c  mov     rcx, rbx; hMem
0x18000209f  add     rsi, rsi
0x1800020a2  call    cs:__imp_LocalFree
0x1800020a8  mov     eax, 2
0x1800020ad  mov     [rsp+10A8h+var_1068], 0
0x1800020b6  mul     rsi
0x1800020b9  test    rdx, rdx
0x1800020bc  jnz     loc_180002147
0x1800020c2  mov     rdx, rax; uBytes
0x1800020c5  mov     ecx, 40h ; '@'; uFlags
0x1800020ca  call    cs:__imp_LocalAlloc
0x1800020d0  mov     rbx, rax
0x1800020d3  neg     rax
0x1800020d6  sbb     ecx, ecx
0x1800020d8  not     ecx
0x1800020da  and     ecx, 8007000Eh
0x1800020e0  test    rbx, rbx
0x1800020e3  jz      short loc_18000214E
0x1800020e5  test    rsi, rsi
0x1800020e8  jz      short loc_180002136
0x1800020ea  cmp     rsi, 7FFFFFFFh
0x1800020f1  jbe     short loc_1800020FA
0x1800020f3  mov     ecx, 80070057h
0x1800020f8  jmp     short loc_180002140
0x1800020fa  lea     rdi, [rsi-1]
0x1800020fe  mov     r9, r12; Args
0x180002101  mov     rdx, rdi; BufferCount
0x180002104  mov     r8, r15; Format
0x180002107  mov     rcx, rbx; Buffer
0x18000210a  call    _vsnwprintf
0x18000210f  test    eax, eax
0x180002111  js      short loc_180002129
0x180002113  cdqe
0x180002115  cmp     rax, rdi
0x180002118  ja      short loc_180002129
0x18000211a  xor     ecx, ecx
0x18000211c  cmp     rax, rdi
0x18000211f  jnz     short loc_18000214E
0x180002121  xor     eax, eax
0x180002123  mov     [rbx+rdi*2], ax
0x180002127  jmp     short loc_18000214E
0x180002129  xor     eax, eax
0x18000212b  mov     ecx, 8007007Ah
0x180002130  mov     [rbx+rdi*2], ax
0x180002134  jmp     short loc_18000214E
0x180002136  mov     ecx, 80070057h
0x18000213b  test    rsi, rsi
0x18000213e  jz      short loc_18000214E
0x180002140  xor     eax, eax
0x180002142  mov     [rbx], ax
0x180002145  jmp     short loc_18000214E
0x180002147  xor     ebx, ebx
0x180002149  mov     ecx, 80070216h
0x18000214e  cmp     ecx, 8007007Ah
0x180002154  jz      loc_18000209C
0x18000215a  test    ecx, ecx
0x18000215c  js      short loc_1800021BE
0x18000215e  movzx   ecx, bp
0x180002161  sub     ecx, 1
0x180002164  jz      short loc_1800021B1
0x180002166  sub     ecx, 1
0x180002169  jz      short loc_1800021B1
0x18000216b  cmp     ecx, 1
0x18000216e  jz      short loc_1800021B1
0x180002170  lea     rax, aFailed; "Failed"
0x180002177  mov     r8d, 55h ; 'U'; unsigned int
0x18000217d  mov     [rsp+10A8h+var_1078], rax
0x180002182  lea     r9, aLogmessagev; "LogMessageV"
0x180002189  lea     rax, a0; "0"
0x180002190  mov     [rsp+10A8h+var_1080], rax
0x180002195  lea     rdx, aOnecoreuapEndu; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000219c  lea     rax, aAssertSS; "Assert (%s): %s"
0x1800021a3  lea     ecx, [r8-54h]; unsigned int
0x1800021a7  mov     [rsp+10A8h+var_1088], rax; unsigned __int16 *
0x1800021ac  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x1800021b1  mov     r8, r13; char *
0x1800021b4  mov     rdx, rbx; unsigned __int16 *
0x1800021b7  mov     ecx, ebp; int
0x1800021b9  call    ?LogSimpleMessage@@YAXHPEBGPEBD@Z; LogSimpleMessage(int,ushort const *,char const *)
0x1800021be  lea     rax, [rsp+10A8h+Buffer]
0x1800021c3  cmp     rbx, rax
0x1800021c6  jz      short loc_1800021D1
0x1800021c8  mov     rcx, rbx; hMem
0x1800021cb  call    cs:__imp_LocalFree
0x1800021d1  mov     ecx, r14d; dwErrCode
0x1800021d4  call    cs:__imp_SetLastError
0x1800021da  mov     rcx, [rsp+10A8h+var_58]
0x1800021e2  xor     rcx, rsp; StackCookie
0x1800021e5  call    __security_check_cookie
0x1800021ea  add     rsp, 1068h
0x1800021f1  pop     r15
0x1800021f3  pop     r14
0x1800021f5  pop     r13
0x1800021f7  pop     r12
0x1800021f9  pop     rdi
0x1800021fa  pop     rsi
0x1800021fb  pop     rbp
0x1800021fc  pop     rbx
0x1800021fd  retn
```
