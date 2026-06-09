# sub_404FBE

- ea: `0x404fbe`
- end: `0x405054`
- name: `sub_404FBE`
- size: `150`
- prototype: `bool __thiscall(void *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x405054`

## callees

- `0x402330`
- `0x4045df`
- `0x404fbe`
- `0x405120`
- `0x40d08d`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x40501b`
- `KERNEL32!GetProcAddress` at `0x40501b`
- `KERNEL32!FreeLibrary` at `0x405033`
- `KERNEL32!FreeLibrary` at `0x405033`

## string_xrefs

- `0x405004`: `NetApi32.dll`

## pseudocode

```c
bool __thiscall sub_404FBE(void *this)
{
  signed __int32 v1; // esi
  int v2; // ecx
  int v3; // ebx
  HMODULE v4; // eax
  HMODULE v5; // esi
  FARPROC NetFreeAadJoinInformation; // eax
  int v8; // [esp+0h] [ebp-8h] BYREF

  if ( dword_43DA78 == -1 )
  {
    v1 = 0;
    v8 = 0;
    v2 = sub_4045DF((int)this, (int)&v8);
    if ( v2 >= 0 )
      v1 = v8 != 0;
    _InterlockedCompareExchange(&dword_43DA78, v1, -1);
    if ( v2 >= 0 )
    {
      v3 = v8;
      v4 = sub_405120((wchar_t *)L"NetApi32.dll");
      v5 = v4;
      if ( v4 )
      {
        NetFreeAadJoinInformation = GetProcAddress(v4, "NetFreeAadJoinInformation");
        if ( NetFreeAadJoinInformation )
          ((void (__thiscall *)(FARPROC, int))NetFreeAadJoinInformation)(NetFreeAadJoinInformation, v3);
        FreeLibrary(v5);
      }
    }
  }
  return dword_43DA78 == 1;
}

```

## disassembly

```asm
0x404fbe  push    ebp
0x404fbf  mov     ebp, esp
0x404fc1  push    ecx
0x404fc2  push    ecx
0x404fc3  mov     eax, ___security_cookie
0x404fc8  xor     eax, ebp
0x404fca  mov     [ebp+var_4], eax
0x404fcd  cmp     dword_43DA78, 0FFFFFFFFh
0x404fd4  jnz     short loc_40503C
0x404fd6  push    esi
0x404fd7  xor     esi, esi
0x404fd9  lea     edx, [ebp+var_8]
0x404fdc  mov     [ebp+var_8], esi
0x404fdf  call    sub_4045DF
0x404fe4  mov     ecx, eax
0x404fe6  test    ecx, ecx
0x404fe8  js      short loc_404FF0
0x404fea  cmp     [ebp+var_8], esi
0x404fed  jz      short loc_404FF0
0x404fef  inc     esi
0x404ff0  mov     edx, offset dword_43DA78
0x404ff5  or      eax, 0FFFFFFFFh
0x404ff8  lock cmpxchg [edx], esi
0x404ffc  test    ecx, ecx
0x404ffe  js      short loc_40503B
0x405000  push    ebx
0x405001  mov     ebx, [ebp+var_8]
0x405004  mov     ecx, offset aNetapi32Dll_0; "NetApi32.dll"
0x405009  call    sub_405120
0x40500e  mov     esi, eax
0x405010  test    esi, esi
0x405012  jz      short loc_40503A
0x405014  push    edi
0x405015  push    offset aNetfreeaadjoin; "NetFreeAadJoinInformation"
0x40501a  push    esi; hModule
0x40501b  call    ds:GetProcAddress
0x405021  mov     edi, eax
0x405023  test    edi, edi
0x405025  jz      short loc_405032
0x405027  push    ebx
0x405028  mov     ecx, edi
0x40502a  call    ds:___guard_check_icall_fptr
0x405030  call    edi
0x405032  push    esi; hLibModule
0x405033  call    ds:FreeLibrary
0x405039  pop     edi
0x40503a  pop     ebx
0x40503b  pop     esi
0x40503c  mov     eax, dword_43DA78
0x405041  mov     ecx, [ebp+var_4]
0x405044  dec     eax
0x405045  neg     eax
0x405047  sbb     al, al
0x405049  xor     ecx, ebp; StackCookie
0x40504b  inc     al
0x40504d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x405052  leave
0x405053  retn
```
