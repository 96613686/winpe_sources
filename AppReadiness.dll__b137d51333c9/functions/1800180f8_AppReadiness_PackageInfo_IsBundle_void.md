# AppReadiness::PackageInfo::IsBundle(void)

- ea: `0x1800180f8`
- end: `0x180018236`
- name: `?IsBundle@PackageInfo@AppReadiness@@QEAA_NXZ`
- size: `318`
- prototype: `bool __fastcall(AppReadiness::PackageInfo *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017e74`
- `0x18006a160`

## callees

- `0x1800180f8`
- `0x180027a4c`
- `0x18003ecb4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800181fb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800181fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018167`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018167`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018214`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018214`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x180018151`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x18001818c`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x180018151`
- `ext-ms-win-kernel32-package-l1-1-0!PackageIdFromFullName` at `0x18001818c`

## string_xrefs

- `0x1800181aa`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x1800181b6`: `AppReadiness::PackageInfo::IsBundle`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall AppReadiness::PackageInfo::IsBundle(AppReadiness::PackageInfo *this)
{
  char *v2; // rbx
  const WCHAR *v3; // rcx
  BYTE *v4; // rax
  LPCWCH *v5; // rsi
  int v6; // eax
  bool v7; // sf
  _BYTE pExceptionObject[48]; // [rsp+30h] [rbp-38h] BYREF
  UINT32 bufferLength; // [rsp+70h] [rbp+8h] BYREF
  BYTE *v11; // [rsp+78h] [rbp+10h]

  if ( !*((_DWORD *)this + 36) )
  {
    *((_DWORD *)this + 36) = 2;
    if ( *((_QWORD *)this + 11) )
    {
      bufferLength = 0;
      v2 = (char *)this + 72;
      v3 = *((_QWORD *)this + 12) <= 7u ? (const WCHAR *)((char *)this + 72) : *(const WCHAR **)v2;
      if ( PackageIdFromFullName(v3, 0, &bufferLength, 0) == 122 )
      {
        v4 = (BYTE *)LocalAlloc(0x40u, bufferLength);
        v5 = (LPCWCH *)v4;
        v11 = v4;
        if ( *((_QWORD *)v2 + 3) > 7u )
          v2 = *(char **)v2;
        v6 = PackageIdFromFullName((PCWSTR)v2, 0, &bufferLength, v4);
        v7 = v6 < 0;
        if ( v6 > 0 )
        {
          v6 = (unsigned __int16)v6 | 0x80070000;
          v7 = v6 < 0;
        }
        if ( v7 )
        {
          Windows::HResultException::HResultException(
            (Windows::HResultException *)pExceptionObject,
            v6,
            "PackageIdFromFullName(m_packageId.c_str(), PACKAGE_INFORMATION_BASIC, &packageIdLen, reinterpret_cast<BYTE*>"
            "(packageId.get()))",
            "AppReadiness::PackageInfo::IsBundle",
            "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
            321);
          throw (Windows::HResultException *)pExceptionObject;
        }
        *((_DWORD *)this + 36) = (CompareStringOrdinal(L"~", -1, v5[4], -1, 0) != 2) + 1;
        LocalFree(v5);
      }
    }
  }
  return *((_DWORD *)this + 36) == 1;
}

```

## disassembly

```asm
0x1800180f8  mov     [rsp+arg_10], rbx
0x1800180fd  mov     [rsp+arg_18], rsi
0x180018102  push    rdi
0x180018103  sub     rsp, 60h
0x180018107  mov     rdi, rcx
0x18001810a  cmp     dword ptr [rcx+90h], 0
0x180018111  jnz     loc_18001821A
0x180018117  mov     dword ptr [rcx+90h], 2
0x180018121  cmp     qword ptr [rcx+58h], 0
0x180018126  jz      loc_18001821A
0x18001812c  mov     [rsp+68h+bufferLength], 0
0x180018134  lea     rbx, [rcx+48h]
0x180018138  cmp     qword ptr [rbx+18h], 7
0x18001813d  jbe     short loc_180018144
0x18001813f  mov     rcx, [rbx]
0x180018142  jmp     short loc_180018147
0x180018144  mov     rcx, rbx; packageFullName
0x180018147  xor     r9d, r9d; buffer
0x18001814a  lea     r8, [rsp+68h+bufferLength]; bufferLength
0x18001814f  xor     edx, edx; flags
0x180018151  call    cs:__imp_PackageIdFromFullName
0x180018157  cmp     eax, 7Ah ; 'z'
0x18001815a  jnz     loc_18001821A
0x180018160  mov     edx, [rsp+68h+bufferLength]; uBytes
0x180018164  lea     ecx, [rax-3Ah]; uFlags
0x180018167  call    cs:__imp_LocalAlloc
0x18001816d  mov     rsi, rax
0x180018170  mov     [rsp+68h+arg_8], rax
0x180018175  cmp     qword ptr [rbx+18h], 7
0x18001817a  jbe     short loc_18001817F
0x18001817c  mov     rbx, [rbx]
0x18001817f  mov     r9, rsi; buffer
0x180018182  lea     r8, [rsp+68h+bufferLength]; bufferLength
0x180018187  xor     edx, edx; flags
0x180018189  mov     rcx, rbx; packageFullName
0x18001818c  call    cs:__imp_PackageIdFromFullName
0x180018192  test    eax, eax
0x180018194  jle     short loc_1800181A0
0x180018196  movzx   eax, ax
0x180018199  or      eax, 80070000h
0x18001819e  test    eax, eax
0x1800181a0  jns     short loc_1800181E2
0x1800181a2  mov     [rsp+68h+var_40], 141h; int
0x1800181aa  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800181b1  mov     qword ptr [rsp+68h+bIgnoreCase], rcx; char *
0x1800181b6  lea     r9, aAppreadinessPa_6; "AppReadiness::PackageInfo::IsBundle"
0x1800181bd  lea     r8, aPackageidfromf_0; "PackageIdFromFullName(m_packageId.c_str"...
0x1800181c4  mov     edx, eax; int
0x1800181c6  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1800181cb  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800181d0  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800181d7  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1800181dc  call    _CxxThrowException_0
0x1800181e2  mov     [rsp+68h+bIgnoreCase], 0; bIgnoreCase
0x1800181ea  or      edx, 0FFFFFFFFh; cchCount1
0x1800181ed  mov     r9d, edx; cchCount2
0x1800181f0  mov     r8, [rsi+20h]; lpString2
0x1800181f4  lea     rcx, asc_180082DE0; "~"
0x1800181fb  call    cs:__imp_CompareStringOrdinal
0x180018201  xor     ecx, ecx
0x180018203  cmp     eax, 2
0x180018206  setnz   cl
0x180018209  inc     ecx
0x18001820b  mov     [rdi+90h], ecx
0x180018211  mov     rcx, rsi; hMem
0x180018214  call    cs:__imp_LocalFree
0x18001821a  cmp     dword ptr [rdi+90h], 1
0x180018221  setz    al
0x180018224  lea     r11, [rsp+68h+var_8]
0x180018229  mov     rbx, [r11+20h]
0x18001822d  mov     rsi, [r11+28h]
0x180018231  mov     rsp, r11
0x180018234  pop     rdi
0x180018235  retn
```
