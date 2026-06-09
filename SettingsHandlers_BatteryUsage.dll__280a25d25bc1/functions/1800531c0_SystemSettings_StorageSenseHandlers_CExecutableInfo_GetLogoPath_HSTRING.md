# SystemSettings::StorageSenseHandlers::CExecutableInfo::GetLogoPath(HSTRING__ * *)

- ea: `0x1800531c0`
- end: `0x180053294`
- name: `?GetLogoPath@CExecutableInfo@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `212`
- prototype: `int(SystemSettings::StorageSenseHandlers::CExecutableInfo *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18001ddbc`
- `0x180021408`
- `0x180021504`
- `0x180021534`
- `0x1800521fc`
- `0x1800531c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053274`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180053274`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800531eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800531eb`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::CExecutableInfo::GetLogoPath(
        SystemSettings::StorageSenseHandlers::CExecutableInfo *this,
        HSTRING *a2)
{
  HSTRING v3; // rcx
  PCWSTR StringRawBuffer; // rax
  const unsigned __int16 *v5; // rsi
  unsigned __int64 v6; // rdi
  int String; // ebx
  PCNZWCH v8; // rbx
  PCNZWCH sourceString; // [rsp+20h] [rbp-28h] BYREF
  UINT32 length[2]; // [rsp+28h] [rbp-20h]
  __int64 v12; // [rsp+30h] [rbp-18h]

  *a2 = 0;
  v3 = (HSTRING)*((_QWORD *)this + 12);
  sourceString = 0;
  *(_QWORD *)length = 0;
  v12 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v3, 0);
  v5 = StringRawBuffer;
  if ( StringRawBuffer )
  {
    v6 = -1;
    do
      ++v6;
    while ( StringRawBuffer[v6] );
    String = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
               (__int64)&sourceString,
               v6);
    if ( String < 0 )
      goto LABEL_10;
    v8 = sourceString;
    StringCchCopyNW((unsigned __int16 *)sourceString, v6 + 1, v5, v6);
    *(_QWORD *)length = v6;
  }
  else
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&sourceString);
    v8 = sourceString;
  }
  if ( *v8 == 64
    || (String = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
                   &sourceString,
                   L",%i",
                   0),
        String >= 0) )
  {
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&sourceString);
    String = WindowsCreateString(sourceString, length[0], a2);
  }
LABEL_10:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&sourceString);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800531c0  push    rbp
0x1800531c2  push    rbx
0x1800531c3  push    rsi
0x1800531c4  push    rdi
0x1800531c5  push    r14
0x1800531c7  push    r15
0x1800531c9  mov     rbp, rsp
0x1800531cc  sub     rsp, 48h
0x1800531d0  xor     r15d, r15d
0x1800531d3  mov     r14, rdx
0x1800531d6  mov     [rdx], r15
0x1800531d9  xor     edx, edx; length
0x1800531db  mov     rcx, [rcx+60h]; string
0x1800531df  mov     [rbp+sourceString], r15
0x1800531e3  mov     qword ptr [rbp+length], r15
0x1800531e7  mov     [rbp+var_18], r15
0x1800531eb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800531f1  mov     rsi, rax
0x1800531f4  test    rax, rax
0x1800531f7  jz      short loc_180053235
0x1800531f9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800531fd  inc     rdi
0x180053200  cmp     [rax+rdi*2], r15w
0x180053205  jnz     short loc_1800531FD
0x180053207  mov     rdx, rdi
0x18005320a  lea     rcx, [rbp+sourceString]
0x18005320e  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x180053213  mov     ebx, eax
0x180053215  test    eax, eax
0x180053217  js      short loc_18005327C
0x180053219  mov     rbx, [rbp+sourceString]
0x18005321d  lea     rdx, [rdi+1]; unsigned __int64
0x180053221  mov     rcx, rbx; unsigned __int16 *
0x180053224  mov     r9, rdi; unsigned __int64
0x180053227  mov     r8, rsi; unsigned __int16 *
0x18005322a  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18005322f  mov     qword ptr [rbp+length], rdi
0x180053233  jmp     short loc_180053242
0x180053235  lea     rcx, [rbp+sourceString]
0x180053239  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18005323e  mov     rbx, [rbp+sourceString]
0x180053242  cmp     word ptr [rbx], 40h ; '@'
0x180053246  lea     rcx, [rbp+sourceString]
0x18005324a  jz      short loc_180053265
0x18005324c  xor     r8d, r8d
0x18005324f  lea     rdx, aI; ",%i"
0x180053256  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18005325b  mov     ebx, eax
0x18005325d  test    eax, eax
0x18005325f  js      short loc_18005327C
0x180053261  lea     rcx, [rbp+sourceString]
0x180053265  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18005326a  mov     edx, [rbp+length]; length
0x18005326d  mov     r8, r14; string
0x180053270  mov     rcx, [rbp+sourceString]; sourceString
0x180053274  call    cs:__imp_WindowsCreateString
0x18005327a  mov     ebx, eax
0x18005327c  lea     rcx, [rbp+sourceString]
0x180053280  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180053285  mov     eax, ebx
0x180053287  add     rsp, 48h
0x18005328b  pop     r15
0x18005328d  pop     r14
0x18005328f  pop     rdi
0x180053290  pop     rsi
0x180053291  pop     rbx
0x180053292  pop     rbp
0x180053293  retn
```
