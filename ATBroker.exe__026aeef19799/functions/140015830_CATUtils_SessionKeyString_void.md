# CATUtils::SessionKeyString(void)

- ea: `0x140015830`
- end: `0x1400158dd`
- name: `?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ`
- size: `173`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000df88`
- `0x14000ea38`
- `0x14000f9c0`
- `0x140011f08`
- `0x1400127f8`

## callees

- `0x14000c19c`
- `0x14000d118`
- `0x140015830`
- `0x140015b00`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14001586f`
- `KERNEL32!GetCurrentProcessId` at `0x14001586f`
- `KERNEL32!ProcessIdToSessionId` at `0x14001587c`
- `KERNEL32!ProcessIdToSessionId` at `0x14001587c`
- `msvcrt!_ltow_s` at `0x140015897`
- `msvcrt!_ltow_s` at `0x140015897`

## string_xrefs

- `0x14001585b`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\Session`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
    ATL::CSimpleStringT<unsigned short,0>::Append(a1, Buffer);
  }
  return a1;
}

```

## disassembly

```asm
0x140015830  mov     [rsp+arg_8], rbx
0x140015835  push    rdi
0x140015836  sub     rsp, 50h
0x14001583a  mov     rax, cs:__security_cookie
0x140015841  xor     rax, rsp
0x140015844  mov     [rsp+58h+var_10], rax
0x140015849  mov     rbx, rcx
0x14001584c  mov     [rsp+58h+var_30], rcx
0x140015851  xor     edi, edi
0x140015853  mov     [rsp+58h+var_34], edi
0x140015857  mov     [rsp+58h+pSessionId], edi
0x14001585b  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x140015862  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140015867  mov     [rsp+58h+var_34], 1
0x14001586f  call    cs:__imp_GetCurrentProcessId
0x140015875  mov     ecx, eax; dwProcessId
0x140015877  lea     rdx, [rsp+58h+pSessionId]; pSessionId
0x14001587c  call    cs:__imp_ProcessIdToSessionId
0x140015882  test    eax, eax
0x140015884  jz      short loc_1400158C1
0x140015886  lea     r9d, [rdi+0Ah]; Radix
0x14001588a  lea     r8d, [rdi+0Ch]; BufferCount
0x14001588e  lea     rdx, [rsp+58h+Buffer]; Buffer
0x140015893  mov     ecx, [rsp+58h+pSessionId]; Value
0x140015897  call    cs:__imp__ltow_s
0x14001589d  test    eax, eax
0x14001589f  jnz     short loc_1400158C1
0x1400158a1  lea     rax, [rsp+58h+Buffer]
0x1400158a6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400158aa  inc     r8
0x1400158ad  cmp     [rax+r8*2], di
0x1400158b2  jnz     short loc_1400158AA
0x1400158b4  lea     rdx, [rsp+58h+Buffer]
0x1400158b9  mov     rcx, rbx
0x1400158bc  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1400158c1  mov     rax, rbx
0x1400158c4  mov     rcx, [rsp+58h+var_10]
0x1400158c9  xor     rcx, rsp; StackCookie
0x1400158cc  call    __security_check_cookie
0x1400158d1  mov     rbx, [rsp+58h+arg_8]
0x1400158d6  add     rsp, 50h
0x1400158da  pop     rdi
0x1400158db  retn
```
