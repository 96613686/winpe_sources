# FwService::Initialize(NET_FW_SERVICE_TYPE_,_tag_FW_PROFILE_TYPE)

- ea: `0x180049fe4`
- end: `0x18004a06b`
- name: `?Initialize@FwService@@AEAAJW4NET_FW_SERVICE_TYPE_@@W4_tag_FW_PROFILE_TYPE@@@Z`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180049da0`

## callees

- `0x180049fe4`

## import_xrefs

- `fwbase!FwResolveIndirectString` at `0x18004a01f`
- `fwbase!FwResolveIndirectString` at `0x18004a01f`
- `fwbase!FwReportReturnError` at `0x18004a03a`
- `fwbase!FwReportReturnError` at `0x18004a04f`
- `fwbase!FwReportReturnError` at `0x18004a03a`
- `fwbase!FwReportReturnError` at `0x18004a04f`
- `fwbase!FwStringCopy` at `0x18004a00a`
- `fwbase!FwStringCopy` at `0x18004a00a`

## string_xrefs

- `0x18004a033`: `FwService::Initialize`
- `0x18004a048`: `FwService::Initialize`

## pseudocode

```c
__int64 __fastcall FwService::Initialize(__int64 a1, int a2, int a3)
{
  __int64 v3; // rdi
  int v4; // ebx

  *(_DWORD *)(a1 + 24) = a2;
  v3 = a1 + 32;
  *(_DWORD *)(a1 + 48) = a3;
  v4 = FwStringCopy((&g_arrEmbeddedContextStrings)[a2], a1 + 32);
  if ( v4 < 0 || (v4 = FwResolveIndirectString(v3), v4 < 0) )
  {
    FwReportReturnError("FwService::Initialize", (unsigned int)v4);
    return (unsigned int)FwReportReturnError("FwService::Initialize", (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180049fe4  mov     [rsp+arg_0], rbx
0x180049fe9  push    rdi
0x180049fea  sub     rsp, 20h
0x180049fee  mov     [rcx+18h], edx
0x180049ff1  lea     rdi, [rcx+20h]
0x180049ff5  mov     [rcx+30h], r8d
0x180049ff9  lea     rax, ?g_arrEmbeddedContextStrings@@3PAPEBGA; ushort const * near * g_arrEmbeddedContextStrings
0x18004a000  movsxd  rcx, edx
0x18004a003  mov     rdx, rdi
0x18004a006  mov     rcx, [rax+rcx*8]
0x18004a00a  call    cs:__imp_FwStringCopy
0x18004a011  nop     dword ptr [rax+rax+00h]
0x18004a016  mov     ebx, eax
0x18004a018  test    eax, eax
0x18004a01a  js      short loc_18004A031
0x18004a01c  mov     rcx, rdi
0x18004a01f  call    cs:__imp_FwResolveIndirectString
0x18004a026  nop     dword ptr [rax+rax+00h]
0x18004a02b  mov     ebx, eax
0x18004a02d  test    eax, eax
0x18004a02f  jns     short loc_18004A05D
0x18004a031  mov     edx, ebx
0x18004a033  lea     rcx, aFwserviceIniti; "FwService::Initialize"
0x18004a03a  call    cs:__imp_FwReportReturnError
0x18004a041  nop     dword ptr [rax+rax+00h]
0x18004a046  mov     edx, ebx
0x18004a048  lea     rcx, aFwserviceIniti; "FwService::Initialize"
0x18004a04f  call    cs:__imp_FwReportReturnError
0x18004a056  nop     dword ptr [rax+rax+00h]
0x18004a05b  mov     ebx, eax
0x18004a05d  mov     eax, ebx
0x18004a05f  mov     rbx, [rsp+28h+arg_0]
0x18004a064  add     rsp, 20h
0x18004a068  pop     rdi
0x18004a069  retn
```
