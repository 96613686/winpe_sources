# FreeQuickLinkPrivInfo(QUICK_LINK_INFO_PRIV *)

- ea: `0x1802fb850`
- end: `0x1802fb902`
- name: `?FreeQuickLinkPrivInfo@@YAXPEAUQUICK_LINK_INFO_PRIV@@@Z`
- size: `178`
- prototype: `void __fastcall(struct QUICK_LINK_INFO_PRIV *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802fb100`
- `0x180313770`

## callees

- `0x180143a7c`
- `0x1802fb908`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fb85c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fb86c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fb87c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fb88c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fb89c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fb8ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fb8bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fb85c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fb86c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fb87c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fb88c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fb89c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fb8ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802fb8bc`

## pseudocode

```c
void __fastcall FreeQuickLinkPrivInfo(struct QUICK_LINK_INFO_PRIV *a1)
{
  unsigned __int16 **v2; // rdx
  unsigned int v3; // ecx

  CoTaskMemFree(*(LPVOID *)a1);
  CoTaskMemFree(*((LPVOID *)a1 + 1));
  CoTaskMemFree(*((LPVOID *)a1 + 2));
  CoTaskMemFree(*((LPVOID *)a1 + 3));
  CoTaskMemFree(*((LPVOID *)a1 + 4));
  CoTaskMemFree(*((LPVOID *)a1 + 5));
  CoTaskMemFree(*((LPVOID *)a1 + 6));
  FreeStringArray(*((_DWORD *)a1 + 14), *((unsigned __int16 ***)a1 + 8));
  v2 = (unsigned __int16 **)*((_QWORD *)a1 + 9);
  v3 = *((_DWORD *)a1 + 15);
  *((_DWORD *)a1 + 14) = 0;
  *((_QWORD *)a1 + 8) = 0;
  FreeStringArray(v3, v2);
  memset_0(a1, 0, 0x58u);
}

```

## disassembly

```asm
0x1802fb850  push    rbx
0x1802fb852  sub     rsp, 20h
0x1802fb856  mov     rbx, rcx
0x1802fb859  mov     rcx, [rcx]; pv
0x1802fb85c  call    cs:__imp_CoTaskMemFree
0x1802fb863  nop     dword ptr [rax+rax+00h]
0x1802fb868  mov     rcx, [rbx+8]; pv
0x1802fb86c  call    cs:__imp_CoTaskMemFree
0x1802fb873  nop     dword ptr [rax+rax+00h]
0x1802fb878  mov     rcx, [rbx+10h]; pv
0x1802fb87c  call    cs:__imp_CoTaskMemFree
0x1802fb883  nop     dword ptr [rax+rax+00h]
0x1802fb888  mov     rcx, [rbx+18h]; pv
0x1802fb88c  call    cs:__imp_CoTaskMemFree
0x1802fb893  nop     dword ptr [rax+rax+00h]
0x1802fb898  mov     rcx, [rbx+20h]; pv
0x1802fb89c  call    cs:__imp_CoTaskMemFree
0x1802fb8a3  nop     dword ptr [rax+rax+00h]
0x1802fb8a8  mov     rcx, [rbx+28h]; pv
0x1802fb8ac  call    cs:__imp_CoTaskMemFree
0x1802fb8b3  nop     dword ptr [rax+rax+00h]
0x1802fb8b8  mov     rcx, [rbx+30h]; pv
0x1802fb8bc  call    cs:__imp_CoTaskMemFree
0x1802fb8c3  nop     dword ptr [rax+rax+00h]
0x1802fb8c8  mov     rdx, [rbx+40h]; unsigned __int16 **
0x1802fb8cc  mov     ecx, [rbx+38h]; unsigned int
0x1802fb8cf  call    ?FreeStringArray@@YAXKPEAPEAG@Z; FreeStringArray(ulong,ushort * *)
0x1802fb8d4  mov     rdx, [rbx+48h]; unsigned __int16 **
0x1802fb8d8  mov     ecx, [rbx+3Ch]; unsigned int
0x1802fb8db  mov     dword ptr [rbx+38h], 0
0x1802fb8e2  mov     qword ptr [rbx+40h], 0
0x1802fb8ea  call    ?FreeStringArray@@YAXKPEAPEAG@Z; FreeStringArray(ulong,ushort * *)
0x1802fb8ef  xor     edx, edx; Val
0x1802fb8f1  mov     rcx, rbx; void *
0x1802fb8f4  lea     r8d, [rdx+58h]; Size
0x1802fb8f8  add     rsp, 20h
0x1802fb8fc  pop     rbx
0x1802fb8fd  jmp     memset_0
```
