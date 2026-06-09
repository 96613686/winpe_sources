# DavParsedateTimetzTimeString(ushort *,_LARGE_INTEGER *)

- ea: `0x180027854`
- end: `0x180027a97`
- name: `?DavParsedateTimetzTimeString@@YAKPEAGPEAT_LARGE_INTEGER@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(unsigned __int16 *, union _LARGE_INTEGER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180027774`

## callees

- `0x18000b7dc`
- `0x180027854`
- `0x18002cfa0`

## import_xrefs

- `msvcrt!wcspbrk` at `0x1800279ad`
- `msvcrt!wcspbrk` at `0x180027a00`
- `msvcrt!wcspbrk` at `0x1800279ad`
- `msvcrt!wcspbrk` at `0x180027a00`
- `msvcrt!_wtoi` at `0x1800278e7`
- `msvcrt!_wtoi` at `0x180027910`
- `msvcrt!_wtoi` at `0x180027939`
- `msvcrt!_wtoi` at `0x180027962`
- `msvcrt!_wtoi` at `0x18002798b`
- `msvcrt!_wtoi` at `0x1800279c2`
- `msvcrt!_wtoi` at `0x180027a12`
- `msvcrt!_wtoi` at `0x1800278e7`
- `msvcrt!_wtoi` at `0x180027910`
- `msvcrt!_wtoi` at `0x180027939`
- `msvcrt!_wtoi` at `0x180027962`
- `msvcrt!_wtoi` at `0x18002798b`
- `msvcrt!_wtoi` at `0x1800279c2`
- `msvcrt!_wtoi` at `0x180027a12`
- `ntdll!RtlTimeFieldsToTime` at `0x180027a26`
- `ntdll!RtlTimeFieldsToTime` at `0x180027a26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027a49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027a49`

## pseudocode

```c
__int64 __fastcall DavParsedateTimetzTimeString(unsigned __int16 *a1, union _LARGE_INTEGER *a2)
{
  __int64 v3; // rax
  unsigned __int16 *v4; // rdi
  unsigned __int16 *v5; // rbx
  CSHORT v6; // ax
  const wchar_t *v7; // rcx
  unsigned __int16 *v8; // rbx
  CSHORT v9; // ax
  const wchar_t *v10; // rcx
  unsigned __int16 *v11; // rbx
  CSHORT v12; // ax
  const wchar_t *v13; // rcx
  unsigned __int16 *v14; // rbx
  CSHORT v15; // ax
  const wchar_t *v16; // rcx
  unsigned __int16 *v17; // rbx
  const wchar_t *v18; // r14
  wchar_t *v19; // rsi
  wchar_t v20; // bx
  const wchar_t *v21; // rbx
  const wchar_t *v22; // rsi
  unsigned int v23; // ebx
  DWORD CurrentThreadId; // eax
  _TIME_FIELDS TimeFields; // [rsp+20h] [rbp-40h] BYREF
  wchar_t v27[8]; // [rsp+30h] [rbp-30h] BYREF
  wchar_t Control[8]; // [rsp+40h] [rbp-20h] BYREF

  wcscpy(Control, L".+-zZ");
  wcscpy(v27, L"+-zZ");
  v3 = -1;
  TimeFields = 0;
  do
    ++v3;
  while ( a1[v3] );
  v4 = &a1[v3];
  v5 = a1 + 4;
  if ( a1 + 4 <= v4 && *v5 == 45 )
  {
    *v5 = 0;
    v6 = _wtoi(a1);
    v7 = v5 + 1;
    TimeFields.Year = v6;
    v8 = v5 + 3;
    if ( v8 <= v4 && *v8 == 45 )
    {
      *v8 = 0;
      v9 = _wtoi(v7);
      v10 = v8 + 1;
      TimeFields.Month = v9;
      v11 = v8 + 3;
      if ( v11 <= v4 && *v11 == 84 )
      {
        *v11 = 0;
        v12 = _wtoi(v10);
        v13 = v11 + 1;
        TimeFields.Day = v12;
        v14 = v11 + 3;
        if ( v14 <= v4 && *v14 == 58 )
        {
          *v14 = 0;
          v15 = _wtoi(v13);
          v16 = v14 + 1;
          TimeFields.Hour = v15;
          v17 = v14 + 3;
          if ( v17 <= v4 && *v17 == 58 )
          {
            *v17 = 0;
            v18 = v17 + 1;
            TimeFields.Minute = _wtoi(v16);
            v19 = v17 + 3;
            if ( v17 + 3 <= v4 && wcspbrk(v17 + 3, Control) == v19 )
            {
              v20 = *v19;
              *v19 = 0;
              TimeFields.Second = _wtoi(v18);
              if ( v20 != 46 )
                goto LABEL_22;
              v21 = v19 + 1;
              v22 = v21;
              if ( v21 < v4 )
              {
                do
                {
                  if ( (unsigned __int16)(*v21 - 48) > 9u )
                    break;
                  ++v21;
                }
                while ( v21 < v4 );
                if ( v21 != v22 && wcspbrk(v21, v27) == v21 )
                {
                  *v21 = 0;
                  TimeFields.Milliseconds = _wtoi(v22);
LABEL_22:
                  v23 = 0;
                  if ( RtlTimeFieldsToTime(&TimeFields, a2) )
                    return v23;
                }
              }
            }
          }
        }
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids, CurrentThreadId);
  }
  return 87;
}

```

## disassembly

```asm
0x180027854  mov     [rsp-38h+arg_10], rbx
0x180027859  push    rbp
0x18002785a  push    rsi
0x18002785b  push    rdi
0x18002785c  push    r12
0x18002785e  push    r13
0x180027860  push    r14
0x180027862  push    r15
0x180027864  mov     rbp, rsp
0x180027867  sub     rsp, 60h
0x18002786b  mov     rax, cs:__security_cookie
0x180027872  xor     rax, rsp
0x180027875  mov     [rbp+var_10], rax
0x180027879  mov     eax, dword ptr cs:aZz+8; "Z"
0x18002787f  mov     r15, rdx
0x180027882  movsd   xmm0, qword ptr cs:aZz; ".+-zZ"
0x18002788a  movsd   qword ptr [rbp+Control], xmm0
0x18002788f  movsd   xmm0, qword ptr cs:aZz_0; "+-zZ"
0x180027897  mov     [rbp+var_18], eax
0x18002789a  movzx   eax, word ptr cs:aZz_0+8; ""
0x1800278a1  movsd   qword ptr [rbp+var_30], xmm0
0x1800278a6  xorps   xmm0, xmm0
0x1800278a9  mov     [rbp+var_28], ax
0x1800278ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800278b1  movups  xmmword ptr [rbp+TimeFields.Year], xmm0
0x1800278b5  xor     r12d, r12d
0x1800278b8  inc     rax
0x1800278bb  cmp     [rcx+rax*2], r12w
0x1800278c0  jnz     short loc_1800278B8
0x1800278c2  lea     rdi, [rcx+rax*2]
0x1800278c6  mov     r13d, 30h ; '0'
0x1800278cc  lea     rbx, [rcx+8]
0x1800278d0  cmp     rbx, rdi
0x1800278d3  ja      loc_180027A30
0x1800278d9  cmp     word ptr [rbx], 2Dh ; '-'
0x1800278dd  jnz     loc_180027A30
0x1800278e3  mov     [rbx], r12w
0x1800278e7  call    cs:__imp__wtoi
0x1800278ed  lea     rcx, [rbx+2]; String
0x1800278f1  mov     [rbp+TimeFields.Year], ax
0x1800278f5  lea     rbx, [rcx+4]
0x1800278f9  cmp     rbx, rdi
0x1800278fc  ja      loc_180027A30
0x180027902  cmp     word ptr [rbx], 2Dh ; '-'
0x180027906  jnz     loc_180027A30
0x18002790c  mov     [rbx], r12w
0x180027910  call    cs:__imp__wtoi
0x180027916  lea     rcx, [rbx+2]; String
0x18002791a  mov     [rbp+TimeFields.Month], ax
0x18002791e  lea     rbx, [rcx+4]
0x180027922  cmp     rbx, rdi
0x180027925  ja      loc_180027A30
0x18002792b  cmp     word ptr [rbx], 54h ; 'T'
0x18002792f  jnz     loc_180027A30
0x180027935  mov     [rbx], r12w
0x180027939  call    cs:__imp__wtoi
0x18002793f  lea     rcx, [rbx+2]; String
0x180027943  mov     [rbp+TimeFields.Day], ax
0x180027947  lea     rbx, [rcx+4]
0x18002794b  cmp     rbx, rdi
0x18002794e  ja      loc_180027A30
0x180027954  cmp     word ptr [rbx], 3Ah ; ':'
0x180027958  jnz     loc_180027A30
0x18002795e  mov     [rbx], r12w
0x180027962  call    cs:__imp__wtoi
0x180027968  lea     rcx, [rbx+2]; String
0x18002796c  mov     [rbp+TimeFields.Hour], ax
0x180027970  lea     rbx, [rcx+4]
0x180027974  cmp     rbx, rdi
0x180027977  ja      loc_180027A30
0x18002797d  cmp     word ptr [rbx], 3Ah ; ':'
0x180027981  jnz     loc_180027A30
0x180027987  mov     [rbx], r12w
0x18002798b  call    cs:__imp__wtoi
0x180027991  lea     r14, [rbx+2]
0x180027995  mov     [rbp+TimeFields.Minute], ax
0x180027999  lea     rsi, [r14+4]
0x18002799d  cmp     rsi, rdi
0x1800279a0  ja      loc_180027A30
0x1800279a6  lea     rdx, [rbp+Control]; Control
0x1800279aa  mov     rcx, rsi; String
0x1800279ad  call    cs:__imp_wcspbrk
0x1800279b3  cmp     rax, rsi
0x1800279b6  jnz     short loc_180027A30
0x1800279b8  movzx   ebx, word ptr [rsi]
0x1800279bb  mov     rcx, r14; String
0x1800279be  mov     [rsi], r12w
0x1800279c2  call    cs:__imp__wtoi
0x1800279c8  mov     [rbp+TimeFields.Second], ax
0x1800279cc  cmp     bx, 2Eh ; '.'
0x1800279d0  jnz     short loc_180027A1C
0x1800279d2  lea     rbx, [rsi+2]
0x1800279d6  mov     rsi, rbx
0x1800279d9  cmp     rbx, rdi
0x1800279dc  jnb     short loc_180027A30
0x1800279de  movzx   eax, word ptr [rbx]
0x1800279e1  sub     ax, r13w
0x1800279e5  cmp     ax, 9
0x1800279e9  ja      short loc_1800279F4
0x1800279eb  add     rbx, 2
0x1800279ef  cmp     rbx, rdi
0x1800279f2  jb      short loc_1800279DE
0x1800279f4  cmp     rbx, rsi
0x1800279f7  jz      short loc_180027A30
0x1800279f9  lea     rdx, [rbp+var_30]; Control
0x1800279fd  mov     rcx, rbx; String
0x180027a00  call    cs:__imp_wcspbrk
0x180027a06  cmp     rax, rbx
0x180027a09  jnz     short loc_180027A30
0x180027a0b  mov     rcx, rsi; String
0x180027a0e  mov     [rbx], r12w
0x180027a12  call    cs:__imp__wtoi
0x180027a18  mov     [rbp+TimeFields.Milliseconds], ax
0x180027a1c  mov     ebx, r12d
0x180027a1f  mov     rdx, r15; Time
0x180027a22  lea     rcx, [rbp+TimeFields]; TimeFields
0x180027a26  call    cs:__imp_RtlTimeFieldsToTime
0x180027a2c  test    al, al
0x180027a2e  jnz     short loc_180027A71
0x180027a30  mov     rax, cs:WPP_GLOBAL_Control
0x180027a37  lea     rcx, WPP_GLOBAL_Control
0x180027a3e  cmp     rax, rcx
0x180027a41  jz      short loc_180027A6C
0x180027a43  test    byte ptr [rax+1Ch], 8
0x180027a47  jz      short loc_180027A6C
0x180027a49  call    cs:__imp_GetCurrentThreadId
0x180027a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a56  lea     r8, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids
0x180027a5d  mov     edx, r13d
0x180027a60  mov     r9d, eax
0x180027a63  mov     rcx, [rcx+10h]
0x180027a67  call    WPP_SF_d
0x180027a6c  mov     ebx, 57h ; 'W'
0x180027a71  mov     eax, ebx
0x180027a73  mov     rcx, [rbp+var_10]
0x180027a77  xor     rcx, rsp; StackCookie
0x180027a7a  call    __security_check_cookie
0x180027a7f  mov     rbx, [rsp+60h+arg_10]
0x180027a87  add     rsp, 60h
0x180027a8b  pop     r15
0x180027a8d  pop     r14
0x180027a8f  pop     r13
0x180027a91  pop     r12
0x180027a93  pop     rdi
0x180027a94  pop     rsi
0x180027a95  pop     rbp
0x180027a96  retn
```
