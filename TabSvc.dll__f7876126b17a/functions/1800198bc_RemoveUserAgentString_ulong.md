# RemoveUserAgentString(ulong)

- ea: `0x1800198bc`
- end: `0x180019923`
- name: `?RemoveUserAgentString@@YAJK@Z`
- size: `103`
- prototype: `__int64 __fastcall(REGSAM samDesired)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800197dc`

## callees

- `0x1800198bc`
- `0x18002b404`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800198d6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800198d6`

## string_xrefs

- `0x1800198c5`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\5.0\User Agent\Post Platform\Tablet PC 2.0`
- `0x1800198ff`: `PENSERVICE_RemoveUserAgentString`

## pseudocode

```c
__int64 __fastcall RemoveUserAgentString(REGSAM samDesired)
{
  unsigned int v1; // ebx

  v1 = RegDeleteKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\5.0\\User Agent\\Post Platform\\Tablet PC 2.0",
         samDesired,
         0);
  if ( v1 && WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      21,
      (unsigned int)WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids,
      (unsigned int)"PENSERVICE_RemoveUserAgentString",
      v1);
  return v1;
}

```

## disassembly

```asm
0x1800198bc  push    rbx
0x1800198be  sub     rsp, 30h
0x1800198c2  mov     r8d, ecx; samDesired
0x1800198c5  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800198cc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800198d3  xor     r9d, r9d; Reserved
0x1800198d6  call    cs:__imp_RegDeleteKeyExW
0x1800198dc  mov     ebx, eax
0x1800198de  test    eax, eax
0x1800198e0  jz      short loc_18001991B
0x1800198e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198e9  lea     rax, WPP_GLOBAL_Control
0x1800198f0  cmp     rcx, rax
0x1800198f3  jz      short loc_18001991B
0x1800198f5  test    byte ptr [rcx+1Ch], 10h
0x1800198f9  jz      short loc_18001991B
0x1800198fb  mov     rcx, [rcx+10h]
0x1800198ff  lea     r9, aPenserviceRemo; "PENSERVICE_RemoveUserAgentString"
0x180019906  mov     edx, 15h
0x18001990b  mov     [rsp+38h+var_18], ebx
0x18001990f  lea     r8, WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids
0x180019916  call    WPP_SF_sd
0x18001991b  mov     eax, ebx
0x18001991d  add     rsp, 30h
0x180019921  pop     rbx
0x180019922  retn
```
