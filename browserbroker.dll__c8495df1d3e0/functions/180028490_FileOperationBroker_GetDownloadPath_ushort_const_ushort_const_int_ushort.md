# FileOperationBroker::GetDownloadPath(ushort const *,ushort const *,int,ushort * *)

- ea: `0x180028490`
- end: `0x1800286c1`
- name: `?GetDownloadPath@FileOperationBroker@@UEAAJPEBG0HPEAPEAG@Z`
- size: `561`
- prototype: `int(FileOperationBroker *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18000d17c`
- `0x18000dc74`
- `0x18000e428`
- `0x180026b10`
- `0x180027828`
- `0x180028490`
- `0x18002988c`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18002855d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18002855d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800285b6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800285b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028640`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028640`

## string_xrefs

- `0x1800286af`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\fileoperationbroker.cpp`

## pseudocode

```c
__int64 __fastcall FileOperationBroker::GetDownloadPath(
        FileOperationBroker *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 **a5)
{
  int PIC; // esi
  LPWSTR ExtensionW; // rax
  int i; // edi
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // rdi
  unsigned __int16 *v13; // rax
  __int64 v14; // r9
  unsigned __int16 **v16; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v17; // [rsp+28h] [rbp-D8h]
  unsigned int v18; // [rsp+30h] [rbp-D0h]
  unsigned int v19[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[526]; // [rsp+52h] [rbp-AEh] BYREF
  WCHAR v22; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v23[526]; // [rsp+262h] [rbp+162h] BYREF
  WCHAR FileName[264]; // [rsp+470h] [rbp+370h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6C8h] [rbp+5C8h]

  v19[0] = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, v19);
  if ( PIC >= 0 )
  {
    pszPath = 0;
    memset_0(v21, 0, 0x206u);
    v22 = 0;
    memset_0(v23, 0, 0x206u);
    FileName[0] = 0;
    memset_0(&FileName[1], 0, 0x206u);
    PIC = StringCchCopyW(&pszPath, 0x104u, a3);
    if ( PIC >= 0 )
    {
      ExtensionW = PathFindExtensionW(&pszPath);
      if ( *ExtensionW )
        *ExtensionW = 0;
      for ( i = 0; ; ++i )
      {
        PIC = anonymous_namespace_::CreateName(a2, 0, (__int64)&v22);
        if ( PIC < 0 )
          return (unsigned int)PIC;
        if ( !a4 || !PathFileExistsW(&v22) )
        {
          PIC = anonymous_namespace_::CreateName(a2, 1, (__int64)FileName);
          if ( PIC < 0 )
            return (unsigned int)PIC;
          if ( !a4 || !(unsigned __int8)anonymous_namespace_::WildcardPathExists(FileName) )
            break;
        }
      }
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&v23[2 * v11 - 2] );
      v12 = v11 + 1;
      *a5 = 0;
      if ( v11 + 1 >= v11 && is_mul_ok(v12, 2u) )
      {
        v13 = (unsigned __int16 *)CoTaskMemAlloc(2 * v12);
        *a5 = v13;
        v14 = v13 == 0 ? 0x8007000E : 0;
        if ( v13 )
        {
          StringCchCopyNExW(v13, v11 + 1, &v22, v11, v16, v17, v18);
          return (unsigned int)PIC;
        }
      }
      else
      {
        v14 = 2147942934LL;
      }
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x24D,
        (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\fileoperationbroker.cpp",
        (const char *)v14,
        (int)v16);
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180028490  mov     [rsp-8+arg_0], rbx
0x180028495  push    rbp
0x180028496  push    rsi
0x180028497  push    rdi
0x180028498  push    r12
0x18002849a  push    r13
0x18002849c  push    r14
0x18002849e  push    r15
0x1800284a0  lea     rbp, [rsp-590h]
0x1800284a8  sub     rsp, 690h
0x1800284af  mov     rax, cs:__security_cookie
0x1800284b6  xor     rax, rsp
0x1800284b9  mov     [rbp+5C0h+var_40], rax
0x1800284c0  mov     r15, [rbp+5C0h+arg_20]
0x1800284c7  xor     r13d, r13d
0x1800284ca  mov     r12, rdx
0x1800284cd  mov     [rsp+6C0h+var_680], r13d
0x1800284d2  lea     rdx, [rsp+6C0h+var_680]; unsigned int *
0x1800284d7  mov     r14d, r9d
0x1800284da  mov     rbx, r8
0x1800284dd  lea     ecx, [r13+1]; unsigned int
0x1800284e1  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x1800284e6  mov     esi, eax
0x1800284e8  test    eax, eax
0x1800284ea  js      loc_180028676
0x1800284f0  mov     edi, 206h
0x1800284f5  mov     [rsp+6C0h+pszPath], r13w
0x1800284fb  mov     r8d, edi; Size
0x1800284fe  lea     rcx, [rsp+6C0h+var_66E]; void *
0x180028503  xor     edx, edx; Val
0x180028505  call    memset_0
0x18002850a  mov     r8d, edi; Size
0x18002850d  mov     [rbp+5C0h+var_460], r13w
0x180028515  xor     edx, edx; Val
0x180028517  lea     rcx, [rbp+5C0h+var_45E]; void *
0x18002851e  call    memset_0
0x180028523  mov     r8d, edi; Size
0x180028526  mov     [rbp+5C0h+FileName], r13w
0x18002852e  xor     edx, edx; Val
0x180028530  lea     rcx, [rbp+5C0h+FileName+2]; void *
0x180028537  call    memset_0
0x18002853c  mov     r8, rbx; unsigned __int16 *
0x18002853f  lea     rcx, [rsp+6C0h+pszPath]; unsigned __int16 *
0x180028544  mov     edx, 104h; unsigned __int64
0x180028549  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002854e  mov     esi, eax
0x180028550  test    eax, eax
0x180028552  js      loc_180028676
0x180028558  lea     rcx, [rsp+6C0h+pszPath]; pszPath
0x18002855d  call    cs:__imp_PathFindExtensionW
0x180028563  mov     rbx, rax
0x180028566  cmp     [rax], r13w
0x18002856a  jz      short loc_180028576
0x18002856c  mov     [rax], r13w
0x180028570  add     rbx, 2
0x180028574  jmp     short loc_180028579
0x180028576  mov     rbx, r13
0x180028579  mov     edi, r13d
0x18002857c  lea     rax, [rbp+5C0h+var_460]
0x180028583  mov     r9d, edi
0x180028586  mov     [rsp+6C0h+var_698], rax; __int64
0x18002858b  lea     rdx, [rsp+6C0h+pszPath]
0x180028590  mov     r8, rbx
0x180028593  mov     byte ptr [rsp+6C0h+var_6A0], r13b; char
0x180028598  mov     rcx, r12; unsigned __int16 *
0x18002859b  call    _anonymous_namespace___CreateName
0x1800285a0  mov     esi, eax
0x1800285a2  test    eax, eax
0x1800285a4  js      loc_180028676
0x1800285aa  test    r14d, r14d
0x1800285ad  jz      short loc_1800285C0
0x1800285af  lea     rcx, [rbp+5C0h+var_460]; pszPath
0x1800285b6  call    cs:__imp_PathFileExistsW
0x1800285bc  test    eax, eax
0x1800285be  jnz     short loc_180028603
0x1800285c0  lea     rax, [rbp+5C0h+FileName]
0x1800285c7  mov     r9d, edi
0x1800285ca  mov     [rsp+6C0h+var_698], rax; unsigned __int64 *
0x1800285cf  lea     rdx, [rsp+6C0h+pszPath]
0x1800285d4  mov     r8, rbx
0x1800285d7  mov     byte ptr [rsp+6C0h+var_6A0], 1; int
0x1800285dc  mov     rcx, r12; unsigned __int16 *
0x1800285df  call    _anonymous_namespace___CreateName
0x1800285e4  mov     esi, eax
0x1800285e6  test    eax, eax
0x1800285e8  js      loc_180028676
0x1800285ee  test    r14d, r14d
0x1800285f1  jz      short loc_18002860F
0x1800285f3  lea     rcx, [rbp+5C0h+FileName]; lpFileName
0x1800285fa  call    _anonymous_namespace___WildcardPathExists
0x1800285ff  test    al, al
0x180028601  jz      short loc_18002860F
0x180028603  mov     eax, 1
0x180028608  add     edi, eax
0x18002860a  jmp     loc_18002857C
0x18002860f  lea     rcx, [rbp+5C0h+var_460]
0x180028616  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002861a  inc     rbx
0x18002861d  cmp     [rcx+rbx*2], r13w
0x180028622  jnz     short loc_18002861A
0x180028624  lea     rdi, [rbx+1]
0x180028628  mov     [r15], r13
0x18002862b  cmp     rdi, rbx
0x18002862e  jb      short loc_1800286A2
0x180028630  mov     eax, 2
0x180028635  mul     rdi
0x180028638  test    rdx, rdx
0x18002863b  jnz     short loc_1800286A2
0x18002863d  mov     rcx, rax; cb
0x180028640  call    cs:__imp_CoTaskMemAlloc
0x180028646  mov     rcx, rax
0x180028649  mov     [r15], rax
0x18002864c  neg     rcx
0x18002864f  sbb     r9d, r9d
0x180028652  not     r9d
0x180028655  and     r9d, 8007000Eh
0x18002865c  test    rax, rax
0x18002865f  jz      short loc_1800286A8
0x180028661  mov     r9, rbx; unsigned __int64
0x180028664  lea     r8, [rbp+5C0h+var_460]; unsigned __int16 *
0x18002866b  mov     rdx, rdi; unsigned __int64
0x18002866e  mov     rcx, rax; unsigned __int16 *
0x180028671  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180028676  mov     eax, esi
0x180028678  mov     rcx, [rbp+5C0h+var_40]
0x18002867f  xor     rcx, rsp; StackCookie
0x180028682  call    __security_check_cookie
0x180028687  mov     rbx, [rsp+6C0h+arg_0]
0x18002868f  add     rsp, 690h
0x180028696  pop     r15
0x180028698  pop     r14
0x18002869a  pop     r13
0x18002869c  pop     r12
0x18002869e  pop     rdi
0x18002869f  pop     rsi
0x1800286a0  pop     rbp
0x1800286a1  retn
0x1800286a2  mov     r9d, 80070216h; char *
0x1800286a8  mov     rcx, [rbp+5C8h]; this
0x1800286af  lea     r8, aOnecoreuapInet_7; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x1800286b6  mov     edx, 24Dh; void *
0x1800286bb  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
