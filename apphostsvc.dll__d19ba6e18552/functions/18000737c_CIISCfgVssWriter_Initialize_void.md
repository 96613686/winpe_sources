# CIISCfgVssWriter::Initialize(void)

- ea: `0x18000737c`
- end: `0x18000749e`
- name: `?Initialize@CIISCfgVssWriter@@QEAAHXZ`
- size: `290`
- prototype: `__int64 __fastcall(CIISCfgVssWriter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007120`

## callees

- `0x18000737c`
- `0x18000a010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180007479`
- `iisutil!PuDbgPrint` at `0x180007479`
- `ext-ms-win-fs-vssapi-l1-1-0!CreateWriter` at `0x1800073b4`
- `ext-ms-win-fs-vssapi-l1-1-0!CreateWriter` at `0x1800073b4`

## string_xrefs

- `0x1800073c7`: `IIS Config Writer`
- `0x180007460`: `CIISCfgVssWriter::Initialize`
- `0x180007472`: `servercommon\inetsrv\iis\iisrearc\core\ap\apphostsvc\dll\cfgwriter.cxx`

## pseudocode

```c
__int64 __fastcall CIISCfgVssWriter::Initialize(CIISCfgVssWriter *this)
{
  _QWORD *v1; // rdi
  int Writer; // ebx
  __int64 v3; // rcx
  __int64 (__fastcall *v4)(__int64, __int128 *, const wchar_t *, _QWORD, _DWORD, _DWORD, int, int, int, int, int, char); // rax
  char v6; // [rsp+58h] [rbp-40h]
  __int128 v7; // [rsp+70h] [rbp-28h] BYREF

  v1 = (_QWORD *)((char *)g_pIISCfgVssWriter + 8);
  if ( *((_QWORD *)g_pIISCfgVssWriter + 1) )
  {
    Writer = -2147467259;
  }
  else
  {
    Writer = CreateWriter(g_pIISCfgVssWriter, (char *)g_pIISCfgVssWriter + 8);
    if ( Writer >= 0 )
    {
      v3 = *v1;
      v6 = 0;
      v4 = *(__int64 (__fastcall **)(__int64, __int128 *, const wchar_t *, _QWORD, _DWORD, _DWORD, int, int, int, int, int, char))(*(_QWORD *)*v1 + 24LL);
      v7 = xmmword_18000D688;
      Writer = v4(v3, &v7, L"IIS Config Writer", 0, 0, 0, 2, 3, 3, 60000, 1, v6);
      if ( Writer >= 0 )
        return 1;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v1 + 16LL))(*v1);
      *v1 = 0;
    }
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\apphostsvc\\dll\\cfgwriter.cxx",
      77,
      "CIISCfgVssWriter::Initialize",
      "Error in base object Initialize().  hr = %x\n",
      Writer);
  return 0;
}

```

## disassembly

```asm
0x18000737c  mov     rax, rsp
0x18000737f  mov     [rax+8], rbx
0x180007383  push    rdi
0x180007384  sub     rsp, 90h
0x18000738b  mov     rcx, cs:?g_pIISCfgVssWriter@@3PEAVCIISCfgVssWriter@@EA; CIISCfgVssWriter * g_pIISCfgVssWriter
0x180007392  movaps  xmmword ptr [rax-18h], xmm6
0x180007396  lea     rdi, [rcx+8]
0x18000739a  cmp     qword ptr [rdi], 0
0x18000739e  jz      short loc_1800073AA
0x1800073a0  mov     ebx, 80004005h
0x1800073a5  jmp     loc_180007445
0x1800073aa  movups  xmm6, cs:xmmword_18000D688
0x1800073b1  mov     rdx, rdi
0x1800073b4  call    cs:__imp_CreateWriter
0x1800073ba  mov     ebx, eax
0x1800073bc  test    eax, eax
0x1800073be  js      loc_180007445
0x1800073c4  mov     rcx, [rdi]
0x1800073c7  lea     r8, aIisConfigWrite; "IIS Config Writer"
0x1800073ce  mov     [rsp+98h+var_40], 0
0x1800073d3  lea     rdx, [rsp+98h+var_28]
0x1800073d8  mov     [rsp+98h+var_48], 1
0x1800073e0  xor     r9d, r9d
0x1800073e3  mov     [rsp+98h+var_50], 0EA60h
0x1800073eb  mov     rax, [rcx]
0x1800073ee  mov     [rsp+98h+var_58], 3
0x1800073f6  mov     [rsp+98h+var_60], 3
0x1800073fe  mov     [rsp+98h+var_68], 2
0x180007406  mov     rax, [rax+18h]
0x18000740a  mov     [rsp+98h+var_70], 0
0x180007412  movdqa  [rsp+98h+var_28], xmm6
0x180007418  mov     dword ptr [rsp+98h+var_78], 0
0x180007420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007425  mov     ebx, eax
0x180007427  test    eax, eax
0x180007429  jns     short loc_180007441
0x18000742b  mov     rcx, [rdi]
0x18000742e  mov     rax, [rcx]
0x180007431  mov     rax, [rax+10h]
0x180007435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000743a  mov     qword ptr [rdi], 0
0x180007441  test    ebx, ebx
0x180007443  jns     short loc_180007483
0x180007445  test    byte ptr cs:g_dwDebugFlags, 3
0x18000744c  jz      short loc_18000747F
0x18000744e  mov     rcx, cs:g_pDebug
0x180007455  lea     rax, aErrorInBaseObj; "Error in base object Initialize().  hr "...
0x18000745c  mov     [rsp+98h+var_70], ebx
0x180007460  lea     r9, aCiiscfgvsswrit_1; "CIISCfgVssWriter::Initialize"
0x180007467  mov     r8d, 4Dh ; 'M'
0x18000746d  mov     [rsp+98h+var_78], rax
0x180007472  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180007479  call    cs:__imp_PuDbgPrint
0x18000747f  xor     eax, eax
0x180007481  jmp     short loc_180007488
0x180007483  mov     eax, 1
0x180007488  lea     r11, [rsp+98h+var_8]
0x180007490  mov     rbx, [r11+10h]
0x180007494  movaps  xmm6, xmmword ptr [r11-10h]
0x180007499  mov     rsp, r11
0x18000749c  pop     rdi
0x18000749d  retn
```
