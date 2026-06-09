# RemoteAppUtil::GetSSPWorkspace(ISSPWorkspace * *)

- ea: `0x180019c44`
- end: `0x180019d26`
- name: `?GetSSPWorkspace@RemoteAppUtil@@CAJPEAPEAUISSPWorkspace@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180019d2c`
- `0x18001a098`
- `0x18001a3d8`

## callees

- `0x18000a304`
- `0x180019c44`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180019c92`
- `KERNEL32!GetLastError` at `0x180019ce9`
- `KERNEL32!GetLastError` at `0x180019c92`
- `KERNEL32!GetLastError` at `0x180019ce9`
- `ole32!CoInitializeEx` at `0x180019c5f`
- `ole32!CoInitializeEx` at `0x180019c5f`
- `ole32!CoCreateInstance` at `0x180019cbe`
- `ole32!CoCreateInstance` at `0x180019cbe`

## pseudocode

```c
__int64 __fastcall RemoteAppUtil::GetSSPWorkspace(LPVOID *ppv)
{
  HRESULT Instance; // ebx
  DWORD LastError; // eax
  __int64 v4; // rdx

  *ppv = 0;
  Instance = CoInitializeEx(0, 2u);
  if ( Instance >= 0 )
  {
    Instance = CoCreateInstance(
                 &GUID_0be9f729_a4e0_4bed_9fb3_85f1858143b7,
                 0,
                 1u,
                 &GUID_53a216d0_96fd_4bf0_bc02_b5ab16aa1e39,
                 ppv);
    if ( Instance < 0 && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      LastError = GetLastError();
      v4 = 11;
      goto LABEL_9;
    }
  }
  else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    LastError = GetLastError();
    v4 = 10;
LABEL_9:
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids,
      (unsigned int)Instance,
      LastError);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180019c44  mov     [rsp+arg_0], rbx
0x180019c49  push    rdi
0x180019c4a  sub     rsp, 30h
0x180019c4e  mov     rdi, rcx
0x180019c51  mov     qword ptr [rcx], 0
0x180019c58  xor     ecx, ecx; pvReserved
0x180019c5a  mov     edx, 2; dwCoInit
0x180019c5f  call    cs:__imp_CoInitializeEx
0x180019c66  nop     dword ptr [rax+rax+00h]
0x180019c6b  mov     ebx, eax
0x180019c6d  test    eax, eax
0x180019c6f  jns     short loc_180019CA5
0x180019c71  mov     rax, cs:WPP_GLOBAL_Control
0x180019c78  lea     rcx, WPP_GLOBAL_Control
0x180019c7f  cmp     rax, rcx
0x180019c82  jz      loc_180019D18
0x180019c88  test    byte ptr [rax+1Ch], 4
0x180019c8c  jz      loc_180019D18
0x180019c92  call    cs:__imp_GetLastError
0x180019c99  nop     dword ptr [rax+rax+00h]
0x180019c9e  mov     edx, 0Ah
0x180019ca3  jmp     short loc_180019CFA
0x180019ca5  xor     edx, edx; pUnkOuter
0x180019ca7  mov     [rsp+38h+ppv], rdi; ppv
0x180019cac  lea     r9, _GUID_53a216d0_96fd_4bf0_bc02_b5ab16aa1e39; riid
0x180019cb3  lea     rcx, _GUID_0be9f729_a4e0_4bed_9fb3_85f1858143b7; rclsid
0x180019cba  lea     r8d, [rdx+1]; dwClsContext
0x180019cbe  call    cs:__imp_CoCreateInstance
0x180019cc5  nop     dword ptr [rax+rax+00h]
0x180019cca  mov     ebx, eax
0x180019ccc  test    eax, eax
0x180019cce  jns     short loc_180019D18
0x180019cd0  mov     rdx, cs:WPP_GLOBAL_Control
0x180019cd7  lea     rcx, WPP_GLOBAL_Control
0x180019cde  cmp     rdx, rcx
0x180019ce1  jz      short loc_180019D18
0x180019ce3  test    byte ptr [rdx+1Ch], 4
0x180019ce7  jz      short loc_180019D18
0x180019ce9  call    cs:__imp_GetLastError
0x180019cf0  nop     dword ptr [rax+rax+00h]
0x180019cf5  mov     edx, 0Bh
0x180019cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d01  lea     r8, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids
0x180019d08  mov     r9d, ebx
0x180019d0b  mov     dword ptr [rsp+38h+ppv], eax
0x180019d0f  mov     rcx, [rcx+10h]
0x180019d13  call    WPP_SF_DD
0x180019d18  mov     eax, ebx
0x180019d1a  mov     rbx, [rsp+38h+arg_0]
0x180019d1f  add     rsp, 30h
0x180019d23  pop     rdi
0x180019d24  retn
```
