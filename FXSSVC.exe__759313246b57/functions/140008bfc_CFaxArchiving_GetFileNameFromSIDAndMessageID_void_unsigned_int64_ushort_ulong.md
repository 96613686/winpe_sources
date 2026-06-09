# CFaxArchiving::GetFileNameFromSIDAndMessageID(void *,unsigned __int64,ushort *,ulong)

- ea: `0x140008bfc`
- end: `0x140008d6b`
- name: `?GetFileNameFromSIDAndMessageID@CFaxArchiving@@QEAAKPEAX_KPEAGK@Z`
- size: `367`
- prototype: `__int64 __fastcall(CFaxArchiving *this, void *, __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400066e8`
- `0x14000c5a4`
- `0x14000de90`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140008bfc`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x140008c65`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140008c65`
- `KERNEL32!GetLastError` at `0x140008c75`
- `KERNEL32!GetLastError` at `0x140008c75`
- `KERNEL32!LocalFree` at `0x140008d49`
- `KERNEL32!LocalFree` at `0x140008d49`

## pseudocode

```c
__int64 __fastcall CFaxArchiving::GetFileNameFromSIDAndMessageID(
        CFaxArchiving *this,
        void *a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  DWORD LastError; // eax
  DWORD v8; // ebx
  LPWSTR v10; // r9
  unsigned int v11; // edi
  int v12; // eax
  int v13; // ebx
  LPWSTR StringSid; // [rsp+60h] [rbp+8h] BYREF

  StringSid = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids);
  }
  if ( a2 )
  {
    if ( !ConvertSidToStringSidW(a2, &StringSid) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 181, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, LastError);
      }
      return v8;
    }
    v10 = StringSid;
  }
  else
  {
    v10 = (LPWSTR)L"UnAssigned";
  }
  v11 = 0;
  v12 = StringCchPrintfW(a4, 0x104u, L"%s%s%I64x.%s", v10, L"$", a3, L"tif");
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        182,
        &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        (unsigned int)v12);
    }
    v11 = (unsigned __int16)v13;
    if ( (v13 & 0x1FFF0000) != 0x70000 )
      v11 = v13;
  }
  LocalFree(StringSid);
  return v11;
}

```

## disassembly

```asm
0x140008bfc  mov     rax, rsp
0x140008bff  mov     [rax+10h], rbx
0x140008c03  mov     [rax+18h], rbp
0x140008c07  mov     [rax+8], rcx
0x140008c0b  push    rsi
0x140008c0c  push    rdi
0x140008c0d  push    r15
0x140008c0f  sub     rsp, 40h
0x140008c13  mov     rsi, r9
0x140008c16  mov     qword ptr [rax+8], 0
0x140008c1e  mov     rbp, r8
0x140008c21  mov     rbx, rdx
0x140008c24  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c2b  lea     r15, WPP_GLOBAL_Control
0x140008c32  cmp     rcx, r15
0x140008c35  jz      short loc_140008C58
0x140008c37  test    byte ptr [rcx+1Ch], 4
0x140008c3b  jz      short loc_140008C58
0x140008c3d  cmp     byte ptr [rcx+19h], 5
0x140008c41  jb      short loc_140008C58
0x140008c43  mov     rcx, [rcx+10h]
0x140008c47  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140008c4e  mov     edx, 0B4h
0x140008c53  call    WPP_SF_
0x140008c58  test    rbx, rbx
0x140008c5b  jz      short loc_140008CC1
0x140008c5d  lea     rdx, [rsp+58h+StringSid]; StringSid
0x140008c62  mov     rcx, rbx; Sid
0x140008c65  call    cs:__imp_ConvertSidToStringSidW
0x140008c6c  nop     dword ptr [rax+rax+00h]
0x140008c71  test    eax, eax
0x140008c73  jnz     short loc_140008CBA
0x140008c75  call    cs:__imp_GetLastError
0x140008c7c  nop     dword ptr [rax+rax+00h]
0x140008c81  mov     ebx, eax
0x140008c83  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c8a  cmp     rcx, r15
0x140008c8d  jz      short loc_140008CB3
0x140008c8f  test    byte ptr [rcx+1Ch], 4
0x140008c93  jz      short loc_140008CB3
0x140008c95  cmp     byte ptr [rcx+19h], 2
0x140008c99  jb      short loc_140008CB3
0x140008c9b  mov     rcx, [rcx+10h]
0x140008c9f  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140008ca6  mov     edx, 0B5h
0x140008cab  mov     r9d, eax
0x140008cae  call    WPP_SF_d
0x140008cb3  mov     eax, ebx
0x140008cb5  jmp     loc_140008D57
0x140008cba  mov     r9, [rsp+58h+StringSid]
0x140008cbf  jmp     short loc_140008CC8
0x140008cc1  lea     r9, aUnassigned; "UnAssigned"
0x140008cc8  lea     rax, aTif; "tif"
0x140008ccf  mov     edx, 104h; unsigned __int64
0x140008cd4  mov     [rsp+58h+var_28], rax
0x140008cd9  lea     r8, aSSI64xS; "%s%s%I64x.%s"
0x140008ce0  lea     rax, asc_1400926A0; "$"
0x140008ce7  mov     [rsp+58h+var_30], rbp
0x140008cec  mov     rcx, rsi; unsigned __int16 *
0x140008cef  mov     [rsp+58h+var_38], rax
0x140008cf4  xor     edi, edi
0x140008cf6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008cfb  mov     ebx, eax
0x140008cfd  test    eax, eax
0x140008cff  jns     short loc_140008D44
0x140008d01  mov     rcx, cs:WPP_GLOBAL_Control
0x140008d08  cmp     rcx, r15
0x140008d0b  jz      short loc_140008D31
0x140008d0d  test    byte ptr [rcx+1Ch], 4
0x140008d11  jz      short loc_140008D31
0x140008d13  cmp     byte ptr [rcx+19h], 2
0x140008d17  jb      short loc_140008D31
0x140008d19  mov     rcx, [rcx+10h]
0x140008d1d  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140008d24  mov     edx, 0B6h
0x140008d29  mov     r9d, eax
0x140008d2c  call    WPP_SF_d
0x140008d31  mov     eax, ebx
0x140008d33  movzx   edi, bx
0x140008d36  and     eax, 1FFF0000h
0x140008d3b  cmp     eax, 70000h
0x140008d40  jz      short loc_140008D44
0x140008d42  mov     edi, ebx
0x140008d44  mov     rcx, [rsp+58h+StringSid]; hMem
0x140008d49  call    cs:__imp_LocalFree
0x140008d50  nop     dword ptr [rax+rax+00h]
0x140008d55  mov     eax, edi
0x140008d57  mov     rbx, [rsp+58h+arg_8]
0x140008d5c  mov     rbp, [rsp+58h+arg_10]
0x140008d61  add     rsp, 40h
0x140008d65  pop     r15
0x140008d67  pop     rdi
0x140008d68  pop     rsi
0x140008d69  retn
```
