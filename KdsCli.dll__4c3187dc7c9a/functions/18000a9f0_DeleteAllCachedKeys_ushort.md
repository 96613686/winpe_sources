# DeleteAllCachedKeys(ushort *)

- ea: `0x18000a9f0`
- end: `0x18000abb3`
- name: `?DeleteAllCachedKeys@@YAJPEAG@Z`
- size: `451`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001630`
- `0x180001f64`
- `0x18000a9f0`
- `0x18000abbc`
- `0x18000be6c`
- `0x180010500`
- `0x180010950`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ab7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ab7b`

## string_xrefs

- `0x18000aa4e`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000aa8d`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000ab5b`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`

## pseudocode

```c
__int64 __fastcall DeleteAllCachedKeys(unsigned __int16 *a1)
{
  unsigned __int16 *v2; // rdi
  wchar_t *v3; // rsi
  signed int UserSidStr; // eax
  unsigned int v5; // ebx
  signed int UserStorageArea; // eax
  __int64 v7; // rbx
  unsigned int v8; // r9d
  wchar_t *v9; // r15
  int v10; // eax
  unsigned int v11; // ecx
  HLOCAL hMem; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t *Source; // [rsp+28h] [rbp-D8h] BYREF
  wchar_t Destination[264]; // [rsp+30h] [rbp-D0h] BYREF

  hMem = a1;
  Source = 0;
  v2 = a1;
  v3 = 0;
  if ( a1 )
  {
LABEL_5:
    UserStorageArea = GetUserStorageArea((__int64)v2, 0, &Source);
    v5 = UserStorageArea;
    if ( UserStorageArea < 0 )
    {
      SidKeyDebugTraceError(
        UserStorageArea,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
        0x6C9u);
      v3 = Source;
      goto LABEL_20;
    }
    v3 = Source;
    v7 = -1;
    do
      ++v7;
    while ( Source[v7] );
    if ( wcscpy_s(Destination, 0x105u, Source) )
    {
      v8 = 1748;
    }
    else
    {
      v9 = &Destination[v7];
      if ( wcscpy_s(v9, 261 - v7, L"\\Microsoft\\Crypto\\KdsKey\\") )
      {
        v8 = 1757;
      }
      else
      {
        if ( v9 + 25 > Destination && (unsigned __int64)(v9 + 25 - Destination) <= 0x105 )
        {
          v9[24] = 0;
          v10 = DeleteFolder(Destination);
          v5 = v10;
          if ( v10 >= 0 )
            goto LABEL_20;
          v8 = 1779;
          v11 = v10;
LABEL_19:
          SidKeyDebugTraceError(v11, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx", v8);
          goto LABEL_20;
        }
        v8 = 1768;
      }
    }
    v5 = -2147467259;
    v11 = -2147467259;
    goto LABEL_19;
  }
  UserSidStr = GetUserSidStr((unsigned __int16 **)&hMem);
  v5 = UserSidStr;
  if ( UserSidStr >= 0 )
  {
    v2 = (unsigned __int16 *)hMem;
    goto LABEL_5;
  }
  SidKeyDebugTraceError(
    UserSidStr,
    "hr",
    "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
    0x6BDu);
  v2 = (unsigned __int16 *)hMem;
LABEL_20:
  if ( v2 && v2 != a1 )
    LocalFree(v2);
  if ( v3 )
    SIDKeyProvFree(v3);
  return v5;
}

```

## disassembly

```asm
0x18000a9f0  push    rbp
0x18000a9f2  push    rbx
0x18000a9f3  push    rsi
0x18000a9f4  push    rdi
0x18000a9f5  push    r12
0x18000a9f7  push    r13
0x18000a9f9  push    r14
0x18000a9fb  push    r15
0x18000a9fd  lea     rbp, [rsp-158h]
0x18000aa05  sub     rsp, 258h
0x18000aa0c  mov     rax, cs:__security_cookie
0x18000aa13  xor     rax, rsp
0x18000aa16  mov     [rbp+190h+var_50], rax
0x18000aa1d  xor     r12d, r12d
0x18000aa20  mov     [rsp+290h+hMem], rcx
0x18000aa25  mov     [rsp+290h+Source], r12
0x18000aa2a  mov     r14, rcx
0x18000aa2d  mov     rdi, rcx
0x18000aa30  mov     esi, r12d
0x18000aa33  test    rcx, rcx
0x18000aa36  jnz     short loc_18000AA72
0x18000aa38  lea     rcx, [rsp+290h+hMem]; unsigned __int16 **
0x18000aa3d  call    ?GetUserSidStr@@YAJPEAPEAG@Z; GetUserSidStr(ushort * *)
0x18000aa42  mov     ebx, eax
0x18000aa44  test    eax, eax
0x18000aa46  jns     short loc_18000AA6D
0x18000aa48  mov     r9d, 6BDh; unsigned int
0x18000aa4e  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000aa55  lea     rdx, aHr; "hr"
0x18000aa5c  mov     ecx, eax; unsigned int
0x18000aa5e  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000aa63  mov     rdi, [rsp+290h+hMem]
0x18000aa68  jmp     loc_18000AB6E
0x18000aa6d  mov     rdi, [rsp+290h+hMem]
0x18000aa72  lea     r8, [rsp+290h+Source]
0x18000aa77  xor     edx, edx
0x18000aa79  mov     rcx, rdi
0x18000aa7c  call    GetUserStorageArea
0x18000aa81  mov     ebx, eax
0x18000aa83  test    eax, eax
0x18000aa85  jns     short loc_18000AAAC
0x18000aa87  mov     r9d, 6C9h; unsigned int
0x18000aa8d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000aa94  lea     rdx, aHr; "hr"
0x18000aa9b  mov     ecx, eax; unsigned int
0x18000aa9d  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000aaa2  mov     rsi, [rsp+290h+Source]
0x18000aaa7  jmp     loc_18000AB6E
0x18000aaac  mov     rsi, [rsp+290h+Source]
0x18000aab1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000aab5  inc     rbx
0x18000aab8  cmp     [rsi+rbx*2], r12w
0x18000aabd  jnz     short loc_18000AAB5
0x18000aabf  mov     r13d, 105h
0x18000aac5  lea     rcx, [rsp+290h+Destination]; Destination
0x18000aaca  mov     edx, r13d; SizeInWords
0x18000aacd  mov     r8, rsi; Source
0x18000aad0  call    wcscpy_s
0x18000aad5  test    eax, eax
0x18000aad7  jz      short loc_18000AAE1
0x18000aad9  mov     r9d, 6D4h
0x18000aadf  jmp     short loc_18000AB51
0x18000aae1  lea     r15, [rsp+290h+Destination]
0x18000aae6  mov     rdx, r13
0x18000aae9  lea     r15, [r15+rbx*2]
0x18000aaed  sub     rdx, rbx; SizeInWords
0x18000aaf0  mov     rcx, r15; Destination
0x18000aaf3  lea     r8, aMicrosoftCrypt; "\\Microsoft\\Crypto\\KdsKey\\"
0x18000aafa  call    wcscpy_s
0x18000aaff  test    eax, eax
0x18000ab01  jz      short loc_18000AB0B
0x18000ab03  mov     r9d, 6DDh
0x18000ab09  jmp     short loc_18000AB51
0x18000ab0b  lea     rcx, [r15+32h]
0x18000ab0f  lea     rax, [rsp+290h+Destination]
0x18000ab14  cmp     rcx, rax
0x18000ab17  jbe     short loc_18000AB4B
0x18000ab19  lea     rdx, [rsp+290h+Destination]
0x18000ab1e  mov     rax, rcx
0x18000ab21  sub     rax, rdx
0x18000ab24  sar     rax, 1
0x18000ab27  cmp     rax, r13
0x18000ab2a  ja      short loc_18000AB4B
0x18000ab2c  mov     [rcx-2], r12w
0x18000ab31  lea     rcx, [rsp+290h+Destination]; unsigned __int16 *
0x18000ab36  call    ?DeleteFolder@@YAJPEBG@Z; DeleteFolder(ushort const *)
0x18000ab3b  mov     ebx, eax
0x18000ab3d  test    eax, eax
0x18000ab3f  jns     short loc_18000AB6E
0x18000ab41  mov     r9d, 6F3h
0x18000ab47  mov     ecx, eax
0x18000ab49  jmp     short loc_18000AB5B
0x18000ab4b  mov     r9d, 6E8h; unsigned int
0x18000ab51  mov     ebx, 80004005h
0x18000ab56  mov     ecx, 80004005h; unsigned int
0x18000ab5b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000ab62  lea     rdx, aHr; "hr"
0x18000ab69  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000ab6e  test    rdi, rdi
0x18000ab71  jz      short loc_18000AB81
0x18000ab73  cmp     rdi, r14
0x18000ab76  jz      short loc_18000AB81
0x18000ab78  mov     rcx, rdi; hMem
0x18000ab7b  call    cs:__imp_LocalFree
0x18000ab81  test    rsi, rsi
0x18000ab84  jz      short loc_18000AB8E
0x18000ab86  mov     rcx, rsi; lpMem
0x18000ab89  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000ab8e  mov     eax, ebx
0x18000ab90  mov     rcx, [rbp+190h+var_50]
0x18000ab97  xor     rcx, rsp; StackCookie
0x18000ab9a  call    __security_check_cookie
0x18000ab9f  add     rsp, 258h
0x18000aba6  pop     r15
0x18000aba8  pop     r14
0x18000abaa  pop     r13
0x18000abac  pop     r12
0x18000abae  pop     rdi
0x18000abaf  pop     rsi
0x18000abb0  pop     rbx
0x18000abb1  pop     rbp
0x18000abb2  retn
```
