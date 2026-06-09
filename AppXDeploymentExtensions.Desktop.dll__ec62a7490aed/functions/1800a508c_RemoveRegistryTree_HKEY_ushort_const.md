# RemoveRegistryTree(HKEY__ *,ushort const *)

- ea: `0x1800a508c`
- end: `0x1800a52da`
- name: `?RemoveRegistryTree@@YAJPEAUHKEY__@@PEBG@Z`
- size: `590`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006c7e4`

## callees

- `0x180005020`
- `0x180012fc8`
- `0x1800a457c`
- `0x1800a508c`
- `0x1800a52e0`
- `0x1800aed10`
- `0x1800af918`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a527b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a527b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a528f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a528f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a51ed`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a5250`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a51ed`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a5250`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a52a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a52a5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a515f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a515f`

## string_xrefs

- `0x1800a5132`: `onecore\admin\appmodel\common\removeregistrytree.cpp`
- `0x1800a5193`: `onecore\admin\appmodel\common\removeregistrytree.cpp`

## pseudocode

```c
__int64 __fastcall RemoveRegistryTree(HKEY a1, const unsigned __int16 *a2)
{
  PSID v4; // rdi
  int CurrentUserSidInternal; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  LSTATUS v11; // eax
  HANDLE ProcessHeap; // rax
  PSID Sid; // [rsp+20h] [rbp-E0h] BYREF
  LPWSTR StringSid; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR SubKey; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[526]; // [rsp+32h] [rbp-CEh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v4 = 0;
  Sid = 0;
  StringSid = 0;
  SubKey = 0;
  memset_0(v16, 0, 0x208u);
  if ( a1 == HKEY_LOCAL_MACHINE )
    goto LABEL_14;
  if ( a1 != HKEY_CURRENT_USER )
  {
    if ( a1 != HKEY_USERS )
      return 2147942487LL;
LABEL_14:
    v9 = StringCchCatW(&SubKey, 0x105u, a2);
    v7 = v9;
    if ( v9 < 0 )
    {
      v10 = 285;
      goto LABEL_11;
    }
    if ( RegDeleteTreeW(a1, &SubKey) )
    {
      if ( !v4 )
      {
        CurrentUserSidInternal = GetCurrentUserSidInternal(&Sid);
        v7 = CurrentUserSidInternal;
        if ( CurrentUserSidInternal < 0 )
        {
          v8 = 292;
          goto LABEL_7;
        }
        v4 = Sid;
      }
      v9 = ResetRegTreeSecurityInternal(a1, &SubKey, v4);
      v7 = v9;
      if ( v9 != -2147024894 )
      {
        if ( v9 < 0 )
        {
          v10 = 302;
          goto LABEL_11;
        }
        v11 = RegDeleteTreeW(a1, &SubKey);
        v7 = v11;
        if ( (v11 & 0xFFFFFFFD) != 0 )
        {
          if ( v11 > 0 )
            v7 = (unsigned __int16)v11 | 0x80070000;
          goto LABEL_28;
        }
      }
    }
    v7 = 0;
    goto LABEL_28;
  }
  CurrentUserSidInternal = GetCurrentUserSidInternal(&Sid);
  v7 = CurrentUserSidInternal;
  if ( CurrentUserSidInternal >= 0 )
  {
    v4 = Sid;
    a1 = HKEY_USERS;
    if ( !ConvertSidToStringSidW(Sid, &StringSid) )
      goto LABEL_14;
    v9 = StringCchCatW(&SubKey, 0x105u, StringSid);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v9 = StringCchCatW(&SubKey, 0x105u, L"\\");
      v7 = v9;
      if ( v9 >= 0 )
        goto LABEL_14;
      v10 = 281;
    }
    else
    {
      v10 = 280;
    }
LABEL_11:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
      (const char *)(unsigned int)v9,
      (int)Sid);
    goto LABEL_28;
  }
  v8 = 277;
LABEL_7:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
    (const char *)(unsigned int)CurrentUserSidInternal,
    (int)Sid);
  v4 = Sid;
LABEL_28:
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  if ( StringSid )
    LocalFree(StringSid);
  return v7;
}

```

## disassembly

```asm
0x1800a508c  mov     [rsp-8+arg_10], rbx
0x1800a5091  push    rbp
0x1800a5092  push    rsi
0x1800a5093  push    rdi
0x1800a5094  push    r14
0x1800a5096  push    r15
0x1800a5098  lea     rbp, [rsp-150h]
0x1800a50a0  sub     rsp, 250h
0x1800a50a7  mov     rax, cs:__security_cookie
0x1800a50ae  xor     rax, rsp
0x1800a50b1  mov     [rbp+170h+var_30], rax
0x1800a50b8  mov     r14, rdx
0x1800a50bb  mov     rsi, rcx
0x1800a50be  xor     edi, edi
0x1800a50c0  lea     rcx, [rsp+270h+var_23E]; void *
0x1800a50c5  xor     eax, eax
0x1800a50c7  mov     [rsp+270h+Sid], rdi; int
0x1800a50cc  xor     edx, edx; Val
0x1800a50ce  mov     [rsp+270h+StringSid], rdi
0x1800a50d3  mov     r8d, 208h; Size
0x1800a50d9  mov     [rsp+270h+SubKey], ax
0x1800a50de  call    memset_0
0x1800a50e3  mov     r15d, 105h
0x1800a50e9  cmp     rsi, 0FFFFFFFF80000002h
0x1800a50f0  jz      loc_1800A51C8
0x1800a50f6  cmp     rsi, 0FFFFFFFF80000001h
0x1800a50fd  jz      short loc_1800A5116
0x1800a50ff  cmp     rsi, 0FFFFFFFF80000003h
0x1800a5106  jz      loc_1800A51C8
0x1800a510c  mov     eax, 80070057h
0x1800a5111  jmp     loc_1800A52B3
0x1800a5116  lea     rcx, [rsp+270h+Sid]; void **
0x1800a511b  call    ?GetCurrentUserSidInternal@@YAJPEAPEAX@Z; GetCurrentUserSidInternal(void * *)
0x1800a5120  mov     ebx, eax
0x1800a5122  test    eax, eax
0x1800a5124  jns     short loc_1800A514B
0x1800a5126  mov     edx, 115h; void *
0x1800a512b  mov     rcx, [rbp+178h]; this
0x1800a5132  lea     r8, aOnecoreAdminAp_112; "onecore\\admin\\appmodel\\common\\remov"...
0x1800a5139  mov     r9d, eax; char *
0x1800a513c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a5141  mov     rdi, [rsp+270h+Sid]
0x1800a5146  jmp     loc_1800A5276
0x1800a514b  mov     rdi, [rsp+270h+Sid]
0x1800a5150  lea     rdx, [rsp+270h+StringSid]; StringSid
0x1800a5155  mov     rcx, rdi; Sid
0x1800a5158  mov     rsi, 0FFFFFFFF80000003h
0x1800a515f  call    cs:__imp_ConvertSidToStringSidW
0x1800a5166  nop     dword ptr [rax+rax+00h]
0x1800a516b  test    eax, eax
0x1800a516d  jz      short loc_1800A51C8
0x1800a516f  mov     r8, [rsp+270h+StringSid]; unsigned __int16 *
0x1800a5174  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x1800a5179  mov     rdx, r15; unsigned __int64
0x1800a517c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a5181  mov     ebx, eax
0x1800a5183  test    eax, eax
0x1800a5185  jns     short loc_1800A51A7
0x1800a5187  mov     edx, 118h; void *
0x1800a518c  mov     rcx, [rbp+178h]; this
0x1800a5193  lea     r8, aOnecoreAdminAp_112; "onecore\\admin\\appmodel\\common\\remov"...
0x1800a519a  mov     r9d, eax; char *
0x1800a519d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a51a2  jmp     loc_1800A5276
0x1800a51a7  lea     r8, asc_1801C82A8; "\\"
0x1800a51ae  mov     rdx, r15; unsigned __int64
0x1800a51b1  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x1800a51b6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a51bb  mov     ebx, eax
0x1800a51bd  test    eax, eax
0x1800a51bf  jns     short loc_1800A51C8
0x1800a51c1  mov     edx, 119h
0x1800a51c6  jmp     short loc_1800A518C
0x1800a51c8  mov     r8, r14; unsigned __int16 *
0x1800a51cb  lea     rcx, [rsp+270h+SubKey]; unsigned __int16 *
0x1800a51d0  mov     rdx, r15; unsigned __int64
0x1800a51d3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a51d8  mov     ebx, eax
0x1800a51da  test    eax, eax
0x1800a51dc  jns     short loc_1800A51E5
0x1800a51de  mov     edx, 11Dh
0x1800a51e3  jmp     short loc_1800A518C
0x1800a51e5  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x1800a51ea  mov     rcx, rsi; hKey
0x1800a51ed  call    cs:__imp_RegDeleteTreeW
0x1800a51f4  nop     dword ptr [rax+rax+00h]
0x1800a51f9  test    eax, eax
0x1800a51fb  jz      short loc_1800A5274
0x1800a51fd  test    rdi, rdi
0x1800a5200  jnz     short loc_1800A5221
0x1800a5202  lea     rcx, [rsp+270h+Sid]; void **
0x1800a5207  call    ?GetCurrentUserSidInternal@@YAJPEAPEAX@Z; GetCurrentUserSidInternal(void * *)
0x1800a520c  mov     ebx, eax
0x1800a520e  test    eax, eax
0x1800a5210  jns     short loc_1800A521C
0x1800a5212  mov     edx, 124h
0x1800a5217  jmp     loc_1800A512B
0x1800a521c  mov     rdi, [rsp+270h+Sid]
0x1800a5221  mov     r8, rdi; void *
0x1800a5224  lea     rdx, [rsp+270h+SubKey]; unsigned __int16 *
0x1800a5229  mov     rcx, rsi; HKEY
0x1800a522c  call    ?ResetRegTreeSecurityInternal@@YAJPEAUHKEY__@@PEBGPEAX@Z; ResetRegTreeSecurityInternal(HKEY__ *,ushort const *,void *)
0x1800a5231  mov     ebx, eax
0x1800a5233  cmp     eax, 80070002h
0x1800a5238  jz      short loc_1800A5274
0x1800a523a  test    eax, eax
0x1800a523c  jns     short loc_1800A5248
0x1800a523e  mov     edx, 12Eh
0x1800a5243  jmp     loc_1800A518C
0x1800a5248  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x1800a524d  mov     rcx, rsi; hKey
0x1800a5250  call    cs:__imp_RegDeleteTreeW
0x1800a5257  nop     dword ptr [rax+rax+00h]
0x1800a525c  mov     ebx, eax
0x1800a525e  test    eax, 0FFFFFFFDh
0x1800a5263  jz      short loc_1800A5274
0x1800a5265  test    eax, eax
0x1800a5267  jle     short loc_1800A5276
0x1800a5269  movzx   ebx, ax
0x1800a526c  or      ebx, 80070000h
0x1800a5272  jmp     short loc_1800A5276
0x1800a5274  xor     ebx, ebx
0x1800a5276  test    rdi, rdi
0x1800a5279  jz      short loc_1800A529B
0x1800a527b  call    cs:__imp_GetProcessHeap
0x1800a5282  nop     dword ptr [rax+rax+00h]
0x1800a5287  mov     r8, rdi; lpMem
0x1800a528a  xor     edx, edx; dwFlags
0x1800a528c  mov     rcx, rax; hHeap
0x1800a528f  call    cs:__imp_HeapFree
0x1800a5296  nop     dword ptr [rax+rax+00h]
0x1800a529b  mov     rcx, [rsp+270h+StringSid]; hMem
0x1800a52a0  test    rcx, rcx
0x1800a52a3  jz      short loc_1800A52B1
0x1800a52a5  call    cs:__imp_LocalFree
0x1800a52ac  nop     dword ptr [rax+rax+00h]
0x1800a52b1  mov     eax, ebx
0x1800a52b3  mov     rcx, [rbp+170h+var_30]
0x1800a52ba  xor     rcx, rsp; StackCookie
0x1800a52bd  call    __security_check_cookie
0x1800a52c2  mov     rbx, [rsp+270h+arg_10]
0x1800a52ca  add     rsp, 250h
0x1800a52d1  pop     r15
0x1800a52d3  pop     r14
0x1800a52d5  pop     rdi
0x1800a52d6  pop     rsi
0x1800a52d7  pop     rbp
0x1800a52d8  retn
```
