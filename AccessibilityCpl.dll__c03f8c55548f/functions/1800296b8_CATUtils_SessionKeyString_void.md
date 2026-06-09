# CATUtils::SessionKeyString(void)

- ea: `0x1800296b8`
- end: `0x180029765`
- name: `?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ`
- size: `173`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800224c8`
- `0x180023bc0`
- `0x180028b64`
- `0x180029268`

## callees

- `0x180004310`
- `0x18000539c`
- `0x1800296b8`
- `0x18002d220`

## import_xrefs

- `msvcrt!_ltow_s` at `0x18002971f`
- `msvcrt!_ltow_s` at `0x18002971f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800296f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800296f7`
- `KERNEL32!ProcessIdToSessionId` at `0x180029704`
- `KERNEL32!ProcessIdToSessionId` at `0x180029704`

## string_xrefs

- `0x1800296e3`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\Session`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CATUtils::SessionKeyString(__int64 a1)
{
  DWORD CurrentProcessId; // eax
  __int64 v3; // r8
  DWORD pSessionId[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h]
  wchar_t Buffer[12]; // [rsp+30h] [rbp-28h] BYREF

  v6 = a1;
  pSessionId[0] = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    a1,
    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\Session");
  pSessionId[1] = 1;
  CurrentProcessId = GetCurrentProcessId();
  if ( ProcessIdToSessionId(CurrentProcessId, pSessionId) && !_ltow_s(pSessionId[0], Buffer, 0xCu, 10) )
  {
    v3 = -1;
    do
      ++v3;
    while ( Buffer[v3] );
    ATL::CSimpleStringT<unsigned short,0>::Append(a1, Buffer, v3);
  }
  return a1;
}

```

## disassembly

```asm
0x1800296b8  mov     [rsp+arg_8], rbx
0x1800296bd  push    rdi
0x1800296be  sub     rsp, 50h
0x1800296c2  mov     rax, cs:__security_cookie
0x1800296c9  xor     rax, rsp
0x1800296cc  mov     [rsp+58h+var_10], rax
0x1800296d1  mov     rbx, rcx
0x1800296d4  mov     [rsp+58h+var_30], rcx
0x1800296d9  xor     edi, edi
0x1800296db  mov     [rsp+58h+var_34], edi
0x1800296df  mov     [rsp+58h+pSessionId], edi
0x1800296e3  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800296ea  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800296ef  mov     [rsp+58h+var_34], 1
0x1800296f7  call    cs:__imp_GetCurrentProcessId
0x1800296fd  mov     ecx, eax; dwProcessId
0x1800296ff  lea     rdx, [rsp+58h+pSessionId]; pSessionId
0x180029704  call    cs:__imp_ProcessIdToSessionId
0x18002970a  test    eax, eax
0x18002970c  jz      short loc_180029749
0x18002970e  lea     r9d, [rdi+0Ah]; Radix
0x180029712  lea     r8d, [rdi+0Ch]; BufferCount
0x180029716  lea     rdx, [rsp+58h+Buffer]; Buffer
0x18002971b  mov     ecx, [rsp+58h+pSessionId]; Value
0x18002971f  call    cs:__imp__ltow_s
0x180029725  test    eax, eax
0x180029727  jnz     short loc_180029749
0x180029729  lea     rax, [rsp+58h+Buffer]
0x18002972e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180029732  inc     r8
0x180029735  cmp     [rax+r8*2], di
0x18002973a  jnz     short loc_180029732
0x18002973c  lea     rdx, [rsp+58h+Buffer]
0x180029741  mov     rcx, rbx
0x180029744  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180029749  mov     rax, rbx
0x18002974c  mov     rcx, [rsp+58h+var_10]
0x180029751  xor     rcx, rsp; StackCookie
0x180029754  call    __security_check_cookie
0x180029759  mov     rbx, [rsp+58h+arg_8]
0x18002975e  add     rsp, 50h
0x180029762  pop     rdi
0x180029763  retn
```
