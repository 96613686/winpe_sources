# CFaxArchiving::GetFileNameFromSIDAndMessageID(void *,unsigned __int64,ushort *,ulong)

- ea: `0x140008810`
- end: `0x14000896c`
- name: `?GetFileNameFromSIDAndMessageID@CFaxArchiving@@QEAAKPEAX_KPEAGK@Z`
- size: `348`
- prototype: `__int64 __fastcall(CFaxArchiving *this, void *, __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400064f0`
- `0x14000bf38`
- `0x14000d79c`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140008810`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x140008879`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140008879`
- `KERNEL32!GetLastError` at `0x140008883`
- `KERNEL32!GetLastError` at `0x140008883`
- `KERNEL32!LocalFree` at `0x140008951`
- `KERNEL32!LocalFree` at `0x140008951`

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
0x140008810  mov     rax, rsp
0x140008813  mov     [rax+10h], rbx
0x140008817  mov     [rax+18h], rbp
0x14000881b  mov     [rax+8], rcx
0x14000881f  push    rsi
0x140008820  push    rdi
0x140008821  push    r15
0x140008823  sub     rsp, 40h
0x140008827  mov     rsi, r9
0x14000882a  mov     qword ptr [rax+8], 0
0x140008832  mov     rbp, r8
0x140008835  mov     rbx, rdx
0x140008838  mov     rcx, cs:WPP_GLOBAL_Control
0x14000883f  lea     r15, WPP_GLOBAL_Control
0x140008846  cmp     rcx, r15
0x140008849  jz      short loc_14000886C
0x14000884b  test    byte ptr [rcx+1Ch], 4
0x14000884f  jz      short loc_14000886C
0x140008851  cmp     byte ptr [rcx+19h], 5
0x140008855  jb      short loc_14000886C
0x140008857  mov     rcx, [rcx+10h]
0x14000885b  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140008862  mov     edx, 0B4h
0x140008867  call    WPP_SF_
0x14000886c  test    rbx, rbx
0x14000886f  jz      short loc_1400088C9
0x140008871  lea     rdx, [rsp+58h+StringSid]; StringSid
0x140008876  mov     rcx, rbx; Sid
0x140008879  call    cs:__imp_ConvertSidToStringSidW
0x14000887f  test    eax, eax
0x140008881  jnz     short loc_1400088C2
0x140008883  call    cs:__imp_GetLastError
0x140008889  mov     ebx, eax
0x14000888b  mov     rcx, cs:WPP_GLOBAL_Control
0x140008892  cmp     rcx, r15
0x140008895  jz      short loc_1400088BB
0x140008897  test    byte ptr [rcx+1Ch], 4
0x14000889b  jz      short loc_1400088BB
0x14000889d  cmp     byte ptr [rcx+19h], 2
0x1400088a1  jb      short loc_1400088BB
0x1400088a3  mov     rcx, [rcx+10h]
0x1400088a7  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x1400088ae  mov     edx, 0B5h
0x1400088b3  mov     r9d, eax
0x1400088b6  call    WPP_SF_d
0x1400088bb  mov     eax, ebx
0x1400088bd  jmp     loc_140008959
0x1400088c2  mov     r9, [rsp+58h+StringSid]
0x1400088c7  jmp     short loc_1400088D0
0x1400088c9  lea     r9, aUnassigned; "UnAssigned"
0x1400088d0  lea     rax, aTif; "tif"
0x1400088d7  mov     edx, 104h; unsigned __int64
0x1400088dc  mov     [rsp+58h+var_28], rax
0x1400088e1  lea     r8, aSSI64xS; "%s%s%I64x.%s"
0x1400088e8  lea     rax, asc_14008C690; "$"
0x1400088ef  mov     [rsp+58h+var_30], rbp
0x1400088f4  mov     rcx, rsi; unsigned __int16 *
0x1400088f7  mov     [rsp+58h+var_38], rax
0x1400088fc  xor     edi, edi
0x1400088fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008903  mov     ebx, eax
0x140008905  test    eax, eax
0x140008907  jns     short loc_14000894C
0x140008909  mov     rcx, cs:WPP_GLOBAL_Control
0x140008910  cmp     rcx, r15
0x140008913  jz      short loc_140008939
0x140008915  test    byte ptr [rcx+1Ch], 4
0x140008919  jz      short loc_140008939
0x14000891b  cmp     byte ptr [rcx+19h], 2
0x14000891f  jb      short loc_140008939
0x140008921  mov     rcx, [rcx+10h]
0x140008925  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x14000892c  mov     edx, 0B6h
0x140008931  mov     r9d, eax
0x140008934  call    WPP_SF_d
0x140008939  mov     eax, ebx
0x14000893b  movzx   edi, bx
0x14000893e  and     eax, 1FFF0000h
0x140008943  cmp     eax, 70000h
0x140008948  jz      short loc_14000894C
0x14000894a  mov     edi, ebx
0x14000894c  mov     rcx, [rsp+58h+StringSid]; hMem
0x140008951  call    cs:__imp_LocalFree
0x140008957  mov     eax, edi
0x140008959  mov     rbx, [rsp+58h+arg_8]
0x14000895e  mov     rbp, [rsp+58h+arg_10]
0x140008963  add     rsp, 40h
0x140008967  pop     r15
0x140008969  pop     rdi
0x14000896a  pop     rsi
0x14000896b  retn
```
