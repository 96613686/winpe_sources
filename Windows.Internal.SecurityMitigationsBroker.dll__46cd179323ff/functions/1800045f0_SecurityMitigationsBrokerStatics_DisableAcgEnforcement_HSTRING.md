# SecurityMitigationsBrokerStatics::DisableAcgEnforcement(HSTRING__ *)

- ea: `0x1800045f0`
- end: `0x18000471b`
- name: `?DisableAcgEnforcement@SecurityMitigationsBrokerStatics@@UEAAJPEAUHSTRING__@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(SecurityMitigationsBrokerStatics *this, HSTRING)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000123c`
- `0x18000342c`
- `0x1800045f0`
- `0x180006980`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000460d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000460d`

## pseudocode

```c
__int64 __fastcall SecurityMitigationsBrokerStatics::DisableAcgEnforcement(
        SecurityMitigationsBrokerStatics *this,
        HSTRING a2)
{
  PCWSTR StringRawBuffer; // rax
  __int64 v3; // r8
  __int64 v4; // rdi
  __int64 *v5; // rbx
  int v6; // esi
  __int64 v7; // rax
  const wchar_t *v8; // rcx
  int v9; // eax
  _BYTE v11[16]; // [rsp+30h] [rbp-68h] BYREF
  const wchar_t *v12; // [rsp+40h] [rbp-58h]
  int v13; // [rsp+48h] [rbp-50h]
  int v14; // [rsp+4Ch] [rbp-4Ch]
  __int64 *v15; // [rsp+50h] [rbp-48h]
  int v16; // [rsp+58h] [rbp-40h]
  int v17; // [rsp+5Ch] [rbp-3Ch]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v4 = -1;
  v5 = (__int64 *)StringRawBuffer;
  v6 = 2;
  if ( (Microsoft_Windows_SecurityMitigationsBrokerEnableBits & 4) != 0 )
  {
    if ( StringRawBuffer )
    {
      v7 = -1;
      do
        ++v7;
      while ( *((_WORD *)v5 + v7) );
      v8 = (const wchar_t *)v5;
      v9 = 2 * v7 + 2;
    }
    else
    {
      v8 = L"NULL";
      v9 = 10;
    }
    v13 = v9;
    v12 = v8;
    v14 = 0;
    McGenEventWrite_EventWriteTransfer(v8, UnsupportedArchitecture, v3, 2, v11);
  }
  if ( (unsigned int)dword_18000C048 > 5
    && (qword_18000C058 & 0x400000000000LL) != 0
    && (qword_18000C060 & 0x400000000000LL) == qword_18000C060 )
  {
    if ( v5 )
    {
      do
        ++v4;
      while ( *((_WORD *)v5 + v4) );
      v6 = 2 * v4 + 2;
    }
    else
    {
      v5 = &qword_180009138;
    }
    v15 = v5;
    v16 = v6;
    v17 = 0;
    tlgWriteTransfer_EventWriteTransfer(&dword_18000C048, &unk_180009810, 0, 0, 3, v11);
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x1800045f0  push    rbx
0x1800045f2  push    rbp
0x1800045f3  push    rsi
0x1800045f4  push    rdi
0x1800045f5  sub     rsp, 78h
0x1800045f9  mov     rax, cs:__security_cookie
0x180004600  xor     rax, rsp
0x180004603  mov     [rsp+98h+var_38], rax
0x180004608  mov     rcx, rdx; string
0x18000460b  xor     edx, edx; length
0x18000460d  call    cs:__imp_WindowsGetStringRawBuffer
0x180004613  xor     ebp, ebp
0x180004615  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180004619  test    byte ptr cs:Microsoft_Windows_SecurityMitigationsBrokerEnableBits, 4
0x180004620  mov     rbx, rax
0x180004623  lea     esi, [rbp+2]
0x180004626  jz      short loc_180004677
0x180004628  test    rax, rax
0x18000462b  jz      short loc_180004645
0x18000462d  mov     rax, rdi
0x180004630  inc     rax
0x180004633  cmp     [rbx+rax*2], bp
0x180004637  jnz     short loc_180004630
0x180004639  mov     rcx, rbx
0x18000463c  lea     eax, ds:2[rax*2]
0x180004643  jmp     short loc_180004651
0x180004645  lea     rcx, aNull; "NULL"
0x18000464c  mov     eax, 0Ah
0x180004651  mov     [rsp+98h+var_50], eax
0x180004655  lea     rdx, UnsupportedArchitecture
0x18000465c  lea     rax, [rsp+98h+var_68]
0x180004661  mov     [rsp+98h+var_58], rcx
0x180004666  mov     r9d, esi
0x180004669  mov     [rsp+98h+var_78], rax
0x18000466e  mov     [rsp+98h+var_4C], ebp
0x180004672  call    McGenEventWrite_EventWriteTransfer
0x180004677  mov     eax, cs:dword_18000C048
0x18000467d  cmp     eax, 5
0x180004680  jbe     short loc_180004700
0x180004682  mov     rcx, cs:qword_18000C060
0x180004689  mov     rdx, 400000000000h
0x180004693  mov     rax, cs:qword_18000C058
0x18000469a  test    rdx, rax
0x18000469d  jz      short loc_180004700
0x18000469f  mov     rax, rcx
0x1800046a2  and     rax, rdx
0x1800046a5  cmp     rax, rcx
0x1800046a8  jnz     short loc_180004700
0x1800046aa  test    rbx, rbx
0x1800046ad  jz      short loc_1800046C1
0x1800046af  inc     rdi
0x1800046b2  cmp     [rbx+rdi*2], bp
0x1800046b6  jnz     short loc_1800046AF
0x1800046b8  lea     esi, ds:2[rdi*2]
0x1800046bf  jmp     short loc_1800046C8
0x1800046c1  lea     rbx, qword_180009138
0x1800046c8  lea     rax, [rsp+98h+var_68]
0x1800046cd  mov     [rsp+98h+var_48], rbx
0x1800046d2  mov     [rsp+98h+var_70], rax
0x1800046d7  lea     rdx, unk_180009810
0x1800046de  xor     r9d, r9d
0x1800046e1  mov     dword ptr [rsp+98h+var_78], 3
0x1800046e9  xor     r8d, r8d
0x1800046ec  mov     [rsp+98h+var_40], esi
0x1800046f0  lea     rcx, dword_18000C048
0x1800046f7  mov     [rsp+98h+var_3C], ebp
0x1800046fb  call    _tlgWriteTransfer_EventWriteTransfer
0x180004700  mov     eax, 80004001h
0x180004705  mov     rcx, [rsp+98h+var_38]
0x18000470a  xor     rcx, rsp; StackCookie
0x18000470d  call    __security_check_cookie
0x180004712  add     rsp, 78h
0x180004716  pop     rdi
0x180004717  pop     rsi
0x180004718  pop     rbp
0x180004719  pop     rbx
0x18000471a  retn
```
