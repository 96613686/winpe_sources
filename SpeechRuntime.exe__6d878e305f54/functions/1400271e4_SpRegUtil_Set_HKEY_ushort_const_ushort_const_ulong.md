# SpRegUtil::Set(HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x1400271e4`
- end: `0x1400272f9`
- name: `?Set@SpRegUtil@@SAJPEAUHKEY__@@PEBG1K@Z`
- size: `277`
- prototype: `static int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14002c660`
- `0x14002c830`
- `0x14002c9f0`

## callees

- `0x14000e030`
- `0x14002172c`
- `0x140022fa8`
- `0x1400271e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x14002729c`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x14002729c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140027237`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140027237`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140027288`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140027288`

## pseudocode

```c
__int64 __fastcall SpRegUtil::Set(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, int a4)
{
  unsigned int Key; // eax
  unsigned int v7; // ebx
  HKEY v8; // rbx
  unsigned int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-48h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-48h]
  int dwOptionsb; // [rsp+20h] [rbp-48h]
  HKEY hKey[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY Data; // [rsp+70h] [rbp+8h] BYREF

  Data = a1;
  hKey[0] = 0;
  Key = RegCreateKeyExW(HKEY_CURRENT_USER, a2, 0, 0, 0, 0x20006u, 0, hKey, 0);
  if ( !Key )
  {
    LODWORD(Data) = a4;
    v8 = hKey[0];
    v9 = RegSetValueExW(hKey[0], a3, 0, 4u, (const BYTE *)&Data, 4u);
    if ( v9 )
    {
      v10 = 251;
    }
    else
    {
      v9 = RegFlushKey(v8);
      if ( !v9 )
        goto LABEL_9;
      v10 = 252;
    }
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v10,
            (unsigned int)"onecoreuap\\internal\\enduser\\inc\\sapi\\SpRegUtil.h",
            (const char *)v9,
            dwOptionsa);
    v7 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecoreuap\\internal\\enduser\\inc\\sapi\\SpRegUtil.h",
        (const char *)(unsigned int)v11,
        dwOptionsb);
      goto LABEL_10;
    }
LABEL_9:
    v7 = 0;
    goto LABEL_10;
  }
  v7 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x103,
         (unsigned int)"onecoreuap\\internal\\enduser\\inc\\sapi\\SpRegUtil.h",
         (const char *)Key,
         dwOptions);
LABEL_10:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return v7;
}

```

## disassembly

```asm
0x1400271e4  mov     r11, rsp
0x1400271e7  mov     [r11+10h], rbx
0x1400271eb  mov     [r11+8], rcx
0x1400271ef  push    rdi
0x1400271f0  sub     rsp, 60h
0x1400271f4  mov     qword ptr [r11-28h], 0
0x1400271fc  lea     rax, [r11-18h]
0x140027200  mov     [r11-30h], rax
0x140027204  mov     ebx, r9d
0x140027207  mov     qword ptr [r11-38h], 0
0x14002720f  mov     rdi, r8
0x140027212  mov     [rsp+68h+samDesired], 20006h; samDesired
0x14002721a  xor     r9d, r9d; lpClass
0x14002721d  xor     r8d, r8d; Reserved
0x140027220  mov     [rsp+68h+dwOptions], 0; unsigned int
0x140027228  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14002722f  mov     qword ptr [r11-18h], 0
0x140027237  call    cs:__imp_RegCreateKeyExW
0x14002723d  test    eax, eax
0x14002723f  jz      short loc_140027261
0x140027241  mov     rcx, [rsp+68h]; this
0x140027246  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\enduser\\inc\\sap"...
0x14002724d  mov     r9d, eax; char *
0x140027250  mov     edx, 103h; void *
0x140027255  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14002725a  mov     ebx, eax
0x14002725c  jmp     loc_1400272E2
0x140027261  mov     dword ptr [rsp+68h+Data], ebx
0x140027265  lea     rax, [rsp+68h+Data]
0x14002726a  mov     rbx, [rsp+68h+hKey]
0x14002726f  mov     r9d, 4; dwType
0x140027275  mov     [rsp+68h+samDesired], r9d; cbData
0x14002727a  mov     rcx, rbx; hKey
0x14002727d  xor     r8d, r8d; Reserved
0x140027280  mov     qword ptr [rsp+68h+dwOptions], rax; int
0x140027285  mov     rdx, rdi; lpValueName
0x140027288  call    cs:__imp_RegSetValueExW
0x14002728e  test    eax, eax
0x140027290  jz      short loc_140027299
0x140027292  mov     edx, 0FBh
0x140027297  jmp     short loc_1400272AB
0x140027299  mov     rcx, rbx; hKey
0x14002729c  call    cs:__imp_RegFlushKey
0x1400272a2  test    eax, eax
0x1400272a4  jz      short loc_1400272E0
0x1400272a6  mov     edx, 0FCh; void *
0x1400272ab  mov     rcx, [rsp+68h]; this
0x1400272b0  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\enduser\\inc\\sap"...
0x1400272b7  mov     r9d, eax; char *
0x1400272ba  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400272bf  mov     ebx, eax
0x1400272c1  test    eax, eax
0x1400272c3  jns     short loc_1400272E0
0x1400272c5  mov     rcx, [rsp+68h]; this
0x1400272ca  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\enduser\\inc\\sap"...
0x1400272d1  mov     r9d, eax; char *
0x1400272d4  mov     edx, 104h; void *
0x1400272d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400272de  jmp     short loc_1400272E2
0x1400272e0  xor     ebx, ebx
0x1400272e2  lea     rcx, [rsp+68h+hKey]
0x1400272e7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400272ec  mov     eax, ebx
0x1400272ee  mov     rbx, [rsp+68h+arg_8]
0x1400272f3  add     rsp, 60h
0x1400272f7  pop     rdi
0x1400272f8  retn
```
