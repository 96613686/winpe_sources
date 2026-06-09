# DMClient::DeleteConfigRefreshValue(ushort const *,ushort const *)

- ea: `0x1400584ac`
- end: `0x14005858c`
- name: `?DeleteConfigRefreshValue@DMClient@@YAJPEBG0@Z`
- size: `224`
- prototype: `__int64 __fastcall(DMClient *this, unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140019a6c`

## callees

- `0x1400095b4`
- `0x1400584ac`
- `0x140058594`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058505`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058560`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058572`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058505`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058560`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058572`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14005851e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14005851e`

## pseudocode

```c
__int64 __fastcall DMClient::DeleteConfigRefreshValue(
        DMClient *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  int ConfigRefreshKey; // eax
  unsigned int v5; // ebx
  HKEY v7; // rbx
  LSTATUS v8; // eax
  unsigned int v9; // edi
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HKEY hKey; // [rsp+38h] [rbp+10h] BYREF

  hKey = (HKEY)a2;
  if ( !this )
    return 2147942487LL;
  hKey = 0;
  ConfigRefreshKey = DMClient::GetConfigRefreshKey(this, (const unsigned __int16 *)&hKey, (HKEY *)1, a4);
  v5 = ConfigRefreshKey;
  if ( ConfigRefreshKey >= 0 )
  {
    v7 = hKey;
    v8 = RegDeleteValueW(hKey, L"PausePeriod");
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v9 == -2147024894 || (v9 & 0x80000000) == 0 )
    {
      if ( v7 )
        RegCloseKey(v7);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16B7,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclienttools.cpp",
        (const char *)v9,
        v10);
      if ( v7 )
        RegCloseKey(v7);
      return v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16B2,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\dmclient\\dmclienttools.cpp",
      (const char *)(unsigned int)ConfigRefreshKey,
      v10);
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
}

```

## disassembly

```asm
0x1400584ac  mov     rax, rsp
0x1400584af  mov     [rax+8], rbx
0x1400584b3  mov     [rax+10h], rdx
0x1400584b7  push    rdi; int
0x1400584b8  sub     rsp, 20h
0x1400584bc  test    rcx, rcx
0x1400584bf  jz      loc_14005857C
0x1400584c5  mov     r8d, 1; HKEY *
0x1400584cb  mov     qword ptr [rax+10h], 0
0x1400584d3  lea     rdx, [rax+10h]; unsigned __int16 *
0x1400584d7  call    ?GetConfigRefreshKey@DMClient@@YAJPEBGPEAPEAUHKEY__@@H@Z; DMClient::GetConfigRefreshKey(ushort const *,HKEY__ * *,int)
0x1400584dc  mov     ebx, eax
0x1400584de  test    eax, eax
0x1400584e0  jns     short loc_14005850F
0x1400584e2  mov     rcx, [rsp+28h]; this
0x1400584e7  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1400584ee  mov     r9d, eax; char *
0x1400584f1  mov     edx, 16B2h; void *
0x1400584f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400584fb  mov     rcx, [rsp+28h+hKey]; hKey
0x140058500  test    rcx, rcx
0x140058503  jz      short loc_14005850B
0x140058505  call    cs:__imp_RegCloseKey
0x14005850b  mov     eax, ebx
0x14005850d  jmp     short loc_140058581
0x14005850f  mov     rbx, [rsp+28h+hKey]
0x140058514  lea     rdx, aPauseperiod; "PausePeriod"
0x14005851b  mov     rcx, rbx; hKey
0x14005851e  call    cs:__imp_RegDeleteValueW
0x140058524  mov     edi, eax
0x140058526  test    eax, eax
0x140058528  jle     short loc_140058533
0x14005852a  movzx   edi, ax
0x14005852d  or      edi, 80070000h
0x140058533  cmp     edi, 80070002h
0x140058539  jz      short loc_14005856A
0x14005853b  test    edi, edi
0x14005853d  jns     short loc_14005856A
0x14005853f  mov     rcx, [rsp+28h]; this
0x140058544  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x14005854b  mov     r9d, edi; char *
0x14005854e  mov     edx, 16B7h; void *
0x140058553  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058558  test    rbx, rbx
0x14005855b  jz      short loc_140058566
0x14005855d  mov     rcx, rbx; hKey
0x140058560  call    cs:__imp_RegCloseKey
0x140058566  mov     eax, edi
0x140058568  jmp     short loc_140058581
0x14005856a  test    rbx, rbx
0x14005856d  jz      short loc_140058578
0x14005856f  mov     rcx, rbx; hKey
0x140058572  call    cs:__imp_RegCloseKey
0x140058578  xor     eax, eax
0x14005857a  jmp     short loc_140058581
0x14005857c  mov     eax, 80070057h
0x140058581  mov     rbx, [rsp+28h+arg_0]
0x140058586  add     rsp, 20h
0x14005858a  pop     rdi
0x14005858b  retn
```
