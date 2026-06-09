# SeUtilsGetSystemMode

- ea: `0x180021000`
- end: `0x1800212bc`
- name: `SeUtilsGetSystemMode`
- size: `700`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001f6d0`
- `0x18001f7f8`
- `0x180020a68`
- `0x180020e0c`

## callees

- `0x180021000`
- `0x1800212c4`

## import_xrefs

- `ntdll!wcsrchr` at `0x18002102f`
- `ntdll!wcsrchr` at `0x18002102f`
- `ntdll!wcschr` at `0x1800210be`
- `ntdll!wcschr` at `0x1800210be`
- `ntdll!_wcsnicmp` at `0x180021057`
- `ntdll!_wcsnicmp` at `0x180021094`
- `ntdll!_wcsnicmp` at `0x1800210dd`
- `ntdll!_wcsnicmp` at `0x1800210f7`
- `ntdll!_wcsnicmp` at `0x18002121b`
- `ntdll!_wcsnicmp` at `0x180021239`
- `ntdll!_wcsnicmp` at `0x180021257`
- `ntdll!_wcsnicmp` at `0x180021271`
- `ntdll!_wcsnicmp` at `0x180021057`
- `ntdll!_wcsnicmp` at `0x180021094`
- `ntdll!_wcsnicmp` at `0x1800210dd`
- `ntdll!_wcsnicmp` at `0x1800210f7`
- `ntdll!_wcsnicmp` at `0x18002121b`
- `ntdll!_wcsnicmp` at `0x180021239`
- `ntdll!_wcsnicmp` at `0x180021257`
- `ntdll!_wcsnicmp` at `0x180021271`
- `ntdll!_wcsicmp` at `0x18002110f`
- `ntdll!_wcsicmp` at `0x180021137`
- `ntdll!_wcsicmp` at `0x18002114f`
- `ntdll!_wcsicmp` at `0x180021167`
- `ntdll!_wcsicmp` at `0x18002117f`
- `ntdll!_wcsicmp` at `0x180021197`
- `ntdll!_wcsicmp` at `0x1800211f3`
- `ntdll!_wcsicmp` at `0x18002110f`
- `ntdll!_wcsicmp` at `0x180021137`
- `ntdll!_wcsicmp` at `0x18002114f`
- `ntdll!_wcsicmp` at `0x180021167`
- `ntdll!_wcsicmp` at `0x18002117f`
- `ntdll!_wcsicmp` at `0x180021197`
- `ntdll!_wcsicmp` at `0x1800211f3`

## string_xrefs

- `0x1800210d3`: `\SysWow64\InstallShield\`
- `0x1800210ed`: `\System32\`
- `0x180021105`: `apphelp.dll`

## pseudocode

```c
__int64 __fastcall SeUtilsGetSystemMode(wchar_t *String1)
{
  size_t v1; // rdi
  unsigned __int64 v3; // rbx
  wchar_t *v4; // rax
  wchar_t *v5; // r14
  unsigned int v6; // ebp
  wchar_t v8; // ax
  unsigned __int64 v9; // rax

  v1 = -1;
  v3 = -1;
  do
    ++v3;
  while ( String1[v3] );
  v4 = wcsrchr(String1, 0x5Cu);
  if ( v4 )
    v5 = v4 + 1;
  else
    v5 = String1;
  v6 = 5;
  if ( !_wcsnicmp(L"indiv", v5, 5u) )
  {
    v9 = -1;
    do
      ++v9;
    while ( v5[v9] );
    if ( v9 > 5 && !_wcsicmp(&v5[v9 - 4], L".key") )
      return 6;
  }
  do
    ++v1;
  while ( *(_WORD *)(2 * v1 + 0x7FFE0030) );
  if ( v3 < v1 || _wcsnicmp(String1, (const wchar_t *)0x7FFE0030, v1) )
    return 0;
  v8 = String1[v1];
  if ( !v8 || v8 == 92 && !wcschr(&String1[v1 + 1], 0x5Cu) )
    return 2;
  if ( !_wcsnicmp(L"\\SysWow64\\InstallShield\\", &String1[v1], 0x18u) )
    return 0;
  if ( _wcsnicmp(L"\\System32\\", &String1[v1], 0xAu) && _wcsnicmp(L"\\SysWow64\\", &String1[v1], 0xAu) )
  {
    if ( _wcsnicmp(L"\\AppPatch\\", &String1[v1], 0xAu) )
    {
      if ( !_wcsnicmp(L"\\WinSxS\\", &String1[v1], 8u) )
        return 4;
      if ( !_wcsnicmp(L"\\Microsoft.NET", &String1[v1], 0xEu) )
        return v6;
      return 0;
    }
    return 7;
  }
  if ( !_wcsicmp(v5, L"apphelp.dll") )
    return 1;
  if ( (unsigned int)SdbIsKnownShimDll(v5) )
    return 7;
  if ( !_wcsicmp(v5, L"cmd.exe") )
    return 8;
  if ( !_wcsicmp(v5, L"csrstub.exe") || !_wcsicmp(v5, L"java.exe") || !_wcsicmp(v5, L"javaw.exe") )
    return 0;
  return _wcsicmp(v5, L"javaws.exe") != 0 ? 3 : 0;
}

```

## disassembly

```asm
0x180021000  push    rbx
0x180021002  push    rbp
0x180021003  push    rsi
0x180021004  push    rdi
0x180021005  push    r14
0x180021007  sub     rsp, 20h
0x18002100b  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180021012  mov     rsi, rcx
0x180021015  mov     rbx, rdi
0x180021018  nop     dword ptr [rax+rax+00000000h]
0x180021020  inc     rbx
0x180021023  cmp     word ptr [rcx+rbx*2], 0
0x180021028  jnz     short loc_180021020
0x18002102a  mov     edx, 5Ch ; '\'; Ch
0x18002102f  call    cs:__imp_wcsrchr
0x180021035  mov     r14, rax
0x180021038  test    rax, rax
0x18002103b  jz      loc_1800211B1
0x180021041  add     r14, 2
0x180021045  mov     ebp, 5
0x18002104a  lea     rcx, aIndiv; "indiv"
0x180021051  mov     r8d, ebp; MaxCount
0x180021054  mov     rdx, r14; String2
0x180021057  call    cs:__imp__wcsnicmp
0x18002105d  test    eax, eax
0x18002105f  jz      loc_1800211CB
0x180021065  mov     edx, 7FFE0030h; String2
0x18002106a  nop     word ptr [rax+rax+00h]
0x180021070  inc     rdi
0x180021073  cmp     word ptr [rdx+rdi*2], 0
0x180021078  jnz     short loc_180021070
0x18002107a  cmp     rbx, rdi
0x18002107d  jnb     short loc_18002108E
0x18002107f  xor     ebp, ebp
0x180021081  mov     eax, ebp
0x180021083  add     rsp, 20h
0x180021087  pop     r14
0x180021089  pop     rdi
0x18002108a  pop     rsi
0x18002108b  pop     rbp
0x18002108c  pop     rbx
0x18002108d  retn
0x18002108e  mov     r8, rdi; MaxCount
0x180021091  mov     rcx, rsi; String1
0x180021094  call    cs:__imp__wcsnicmp
0x18002109a  test    eax, eax
0x18002109c  jnz     short loc_18002107F
0x18002109e  movzx   eax, word ptr [rsi+rdi*2]
0x1800210a2  lea     rbx, [rsi+rdi*2]
0x1800210a6  test    ax, ax
0x1800210a9  jz      loc_180021296
0x1800210af  cmp     ax, 5Ch ; '\'
0x1800210b3  jnz     short loc_1800210CD
0x1800210b5  mov     edx, 5Ch ; '\'; Ch
0x1800210ba  lea     rcx, [rbx+2]; Str
0x1800210be  call    cs:__imp_wcschr
0x1800210c4  test    rax, rax
0x1800210c7  jz      loc_180021296
0x1800210cd  mov     r8d, 18h; MaxCount
0x1800210d3  lea     rcx, aSyswow64Instal; "\\SysWow64\\InstallShield\\"
0x1800210da  mov     rdx, rbx; String2
0x1800210dd  call    cs:__imp__wcsnicmp
0x1800210e3  test    eax, eax
0x1800210e5  jz      short loc_18002107F
0x1800210e7  mov     r8d, 0Ah; MaxCount
0x1800210ed  lea     rcx, aSystem32_3; "\\System32\\"
0x1800210f4  mov     rdx, rbx; String2
0x1800210f7  call    cs:__imp__wcsnicmp
0x1800210fd  test    eax, eax
0x1800210ff  jnz     loc_18002120B
0x180021105  lea     rdx, aApphelpDll_1; "apphelp.dll"
0x18002110c  mov     rcx, r14; String1
0x18002110f  call    cs:__imp__wcsicmp
0x180021115  test    eax, eax
0x180021117  jz      loc_180021284
0x18002111d  mov     rcx, r14; String1
0x180021120  call    SdbIsKnownShimDll
0x180021125  test    eax, eax
0x180021127  jnz     loc_1800211B9
0x18002112d  lea     rdx, aCmdExe; "cmd.exe"
0x180021134  mov     rcx, r14; String1
0x180021137  call    cs:__imp__wcsicmp
0x18002113d  test    eax, eax
0x18002113f  jz      loc_1800212B2
0x180021145  lea     rdx, aCsrstubExe; "csrstub.exe"
0x18002114c  mov     rcx, r14; String1
0x18002114f  call    cs:__imp__wcsicmp
0x180021155  test    eax, eax
0x180021157  jz      loc_18002107F
0x18002115d  lea     rdx, aJavaExe; "java.exe"
0x180021164  mov     rcx, r14; String1
0x180021167  call    cs:__imp__wcsicmp
0x18002116d  test    eax, eax
0x18002116f  jz      loc_18002107F
0x180021175  lea     rdx, aJavawExe; "javaw.exe"
0x18002117c  mov     rcx, r14; String1
0x18002117f  call    cs:__imp__wcsicmp
0x180021185  test    eax, eax
0x180021187  jz      loc_18002107F
0x18002118d  lea     rdx, aJavawsExe; "javaws.exe"
0x180021194  mov     rcx, r14; String1
0x180021197  call    cs:__imp__wcsicmp
0x18002119d  neg     eax
0x18002119f  sbb     ecx, ecx
0x1800211a1  and     ecx, 3
0x1800211a4  mov     eax, ecx
0x1800211a6  add     rsp, 20h
0x1800211aa  pop     r14
0x1800211ac  pop     rdi
0x1800211ad  pop     rsi
0x1800211ae  pop     rbp
0x1800211af  pop     rbx
0x1800211b0  retn
0x1800211b1  mov     r14, rsi
0x1800211b4  jmp     loc_180021045
0x1800211b9  mov     ebp, 7
0x1800211be  mov     eax, ebp
0x1800211c0  add     rsp, 20h
0x1800211c4  pop     r14
0x1800211c6  pop     rdi
0x1800211c7  pop     rsi
0x1800211c8  pop     rbp
0x1800211c9  pop     rbx
0x1800211ca  retn
0x1800211cb  mov     rax, rdi
0x1800211ce  xchg    ax, ax
0x1800211d0  inc     rax
0x1800211d3  cmp     word ptr [r14+rax*2], 0
0x1800211d9  jnz     short loc_1800211D0
0x1800211db  cmp     rax, rbp
0x1800211de  jbe     loc_180021065
0x1800211e4  add     rax, 0FFFFFFFFFFFFFFFCh
0x1800211e8  lea     rdx, aKey; ".key"
0x1800211ef  lea     rcx, [r14+rax*2]; String1
0x1800211f3  call    cs:__imp__wcsicmp
0x1800211f9  test    eax, eax
0x1800211fb  jnz     loc_180021065
0x180021201  mov     ebp, 6
0x180021206  jmp     loc_180021081
0x18002120b  mov     r8d, 0Ah; MaxCount
0x180021211  lea     rcx, aSyswow64_0; "\\SysWow64\\"
0x180021218  mov     rdx, rbx; String2
0x18002121b  call    cs:__imp__wcsnicmp
0x180021221  test    eax, eax
0x180021223  jz      loc_180021105
0x180021229  mov     r8d, 0Ah; MaxCount
0x18002122f  lea     rcx, aApppatch; "\\AppPatch\\"
0x180021236  mov     rdx, rbx; String2
0x180021239  call    cs:__imp__wcsnicmp
0x18002123f  test    eax, eax
0x180021241  jz      loc_1800211B9
0x180021247  mov     r8d, 8; MaxCount
0x18002124d  lea     rcx, aWinsxs; "\\WinSxS\\"
0x180021254  mov     rdx, rbx; String2
0x180021257  call    cs:__imp__wcsnicmp
0x18002125d  test    eax, eax
0x18002125f  jz      short loc_1800212A8
0x180021261  mov     r8d, 0Eh; MaxCount
0x180021267  lea     rcx, aMicrosoftNet; "\\Microsoft.NET"
0x18002126e  mov     rdx, rbx; String2
0x180021271  call    cs:__imp__wcsnicmp
0x180021277  test    eax, eax
0x180021279  jz      loc_180021081
0x18002127f  jmp     loc_18002107F
0x180021284  mov     ebp, 1
0x180021289  mov     eax, ebp
0x18002128b  add     rsp, 20h
0x18002128f  pop     r14
0x180021291  pop     rdi
0x180021292  pop     rsi
0x180021293  pop     rbp
0x180021294  pop     rbx
0x180021295  retn
0x180021296  mov     ebp, 2
0x18002129b  mov     eax, ebp
0x18002129d  add     rsp, 20h
0x1800212a1  pop     r14
0x1800212a3  pop     rdi
0x1800212a4  pop     rsi
0x1800212a5  pop     rbp
0x1800212a6  pop     rbx
0x1800212a7  retn
0x1800212a8  mov     ebp, 4
0x1800212ad  jmp     loc_180021081
0x1800212b2  mov     ebp, 8
0x1800212b7  jmp     loc_180021081
```
