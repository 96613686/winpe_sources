# GetSystemStartMode(ESystemStartMode *)

- ea: `0x140007d88`
- end: `0x140007e5c`
- name: `?GetSystemStartMode@@YAJPEAW4ESystemStartMode@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(enum ESystemStartMode *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400068bc`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x140007d88`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140007de7`
- `KERNEL32!IsDebuggerPresent` at `0x140007de7`
- `USER32!GetSystemMetrics` at `0x140007d9c`
- `USER32!GetSystemMetrics` at `0x140007d9c`

## string_xrefs

- `0x140007dd9`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140007df5`: `termsrv\wms\src\common\srcutils\srcutils.cpp`
- `0x140007e25`: `termsrv\wms\src\common\srcutils\srcutils.cpp`

## pseudocode

```c
__int64 __fastcall GetSystemStartMode(enum ESystemStartMode *a1)
{
  int SystemMetrics; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+30h] [rbp-38h]
  int v6; // [rsp+38h] [rbp-30h]

  SystemMetrics = GetSystemMetrics(67);
  if ( SystemMetrics <= 2 )
  {
    v3 = 0;
    *(_DWORD *)a1 = SystemMetrics;
  }
  else
  {
    v3 = -2147418113;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0xC18u,
      L"GetSystemStartMode",
      L"CBRAEx",
      L"iResult <= SSM_SafeModeWithNetwork",
      -2147418113);
    if ( IsDebuggerPresent() )
    {
      v6 = -2147418113;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        3096,
        L"GetSystemStartMode",
        L"CBRAEx",
        L"iResult <= SSM_SafeModeWithNetwork",
        v6);
    }
    else
    {
      v5 = -2147418113;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        3096,
        L"GetSystemStartMode",
        L"CBRAEx",
        L"iResult <= SSM_SafeModeWithNetwork",
        v5);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140007d88  push    rbx
0x140007d8a  push    rbp
0x140007d8b  push    rdi
0x140007d8c  push    r14
0x140007d8e  push    r15
0x140007d90  sub     rsp, 40h
0x140007d94  mov     rdi, rcx
0x140007d97  mov     ecx, 43h ; 'C'; nIndex
0x140007d9c  call    cs:__imp_GetSystemMetrics
0x140007da2  cmp     eax, 2
0x140007da5  jle     loc_140007E4A
0x140007dab  mov     ebx, 8000FFFFh
0x140007db0  lea     r15, aCbraex; "CBRAEx"
0x140007db7  lea     rbp, aGetsystemstart; "GetSystemStartMode"
0x140007dbe  mov     [rsp+68h+var_40], ebx; int
0x140007dc2  mov     edi, 0C18h
0x140007dc7  lea     r14, aIresultSsmSafe; "iResult <= SSM_SafeModeWithNetwork"
0x140007dce  mov     r9, r15; unsigned __int16 *
0x140007dd1  mov     [rsp+68h+var_48], r14; unsigned __int16 *
0x140007dd6  mov     r8, rbp; unsigned __int16 *
0x140007dd9  lea     rcx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140007de0  mov     edx, edi; unsigned int
0x140007de2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007de7  call    cs:__imp_IsDebuggerPresent
0x140007ded  test    eax, eax
0x140007def  jz      short loc_140007E21
0x140007df1  mov     [rsp+68h+var_30], ebx
0x140007df5  lea     r8, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140007dfc  mov     [rsp+68h+var_38], r14
0x140007e01  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140007e08  mov     qword ptr [rsp+68h+var_40], r15
0x140007e0d  mov     r9d, edi
0x140007e10  mov     ecx, 2; unsigned __int8
0x140007e15  mov     [rsp+68h+var_48], rbp
0x140007e1a  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140007e1f  jmp     short loc_140007E4E
0x140007e21  mov     dword ptr [rsp+68h+var_38], ebx
0x140007e25  lea     rdx, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140007e2c  mov     qword ptr [rsp+68h+var_40], r14
0x140007e31  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140007e38  mov     r9, rbp
0x140007e3b  mov     [rsp+68h+var_48], r15
0x140007e40  mov     r8d, edi
0x140007e43  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140007e48  jmp     short loc_140007E4E
0x140007e4a  xor     ebx, ebx
0x140007e4c  mov     [rdi], eax
0x140007e4e  mov     eax, ebx
0x140007e50  add     rsp, 40h
0x140007e54  pop     r15
0x140007e56  pop     r14
0x140007e58  pop     rdi
0x140007e59  pop     rbp
0x140007e5a  pop     rbx
0x140007e5b  retn
```
