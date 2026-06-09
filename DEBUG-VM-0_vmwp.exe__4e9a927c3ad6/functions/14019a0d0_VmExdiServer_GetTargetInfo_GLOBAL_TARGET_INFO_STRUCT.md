# VmExdiServer::GetTargetInfo(_GLOBAL_TARGET_INFO_STRUCT *)

- ea: `0x14019a0d0`
- end: `0x14019a1b8`
- name: `?GetTargetInfo@VmExdiServer@@UEAAJPEAU_GLOBAL_TARGET_INFO_STRUCT@@@Z`
- size: `232`
- prototype: `__int64 __fastcall(VmExdiServer *__hidden this, struct _GLOBAL_TARGET_INFO_STRUCT *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14019a0d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14019a141`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14019a15b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14019a141`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14019a15b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14019a106`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14019a119`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14019a106`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14019a119`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14019a175`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14019a18e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14019a175`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14019a18e`

## pseudocode

```c
__int64 __fastcall VmExdiServer::GetTargetInfo(VmExdiServer *this, struct _GLOBAL_TARGET_INFO_STRUCT *a2)
{
  LPVOID v3; // rax
  void *v4; // rcx
  unsigned int v5; // edi
  void *v6; // rcx

  if ( a2 )
  {
    *(_QWORD *)a2 = 0;
    *((_QWORD *)a2 + 1) = 0;
    *((_QWORD *)a2 + 2) = 0;
    *((_QWORD *)a2 + 3) = 0;
    *((_QWORD *)a2 + 4) = 0;
    *((_DWORD *)a2 + 10) = 0;
    *((_QWORD *)a2 + 6) = CoTaskMemAlloc(0x20u);
    v3 = CoTaskMemAlloc(0x1Eu);
    v4 = (void *)*((_QWORD *)a2 + 6);
    *((_QWORD *)a2 + 7) = v3;
    if ( v4 && v3 )
    {
      _o_wcscpy_s(v4, 16, L"Virtual Machine");
      _o_wcscpy_s(*((_QWORD *)a2 + 7), 15, L"VM EXDI Driver");
      return 0;
    }
    else
    {
      v5 = -528351218;
      if ( v4 )
      {
        CoTaskMemFree(v4);
        *((_QWORD *)a2 + 6) = 0;
      }
      v6 = (void *)*((_QWORD *)a2 + 7);
      if ( v6 )
      {
        CoTaskMemFree(v6);
        *((_QWORD *)a2 + 7) = 0;
      }
    }
  }
  else
  {
    return (unsigned int)-528351145;
  }
  return v5;
}

```

## disassembly

```asm
0x14019a0d0  mov     [rsp+arg_0], rbx
0x14019a0d5  mov     [rsp+arg_8], rsi
0x14019a0da  push    rdi
0x14019a0db  sub     rsp, 20h
0x14019a0df  xor     esi, esi
0x14019a0e1  mov     rbx, rdx
0x14019a0e4  test    rdx, rdx
0x14019a0e7  jz      loc_14019A1A0
0x14019a0ed  lea     ecx, [rsi+20h]; cb
0x14019a0f0  mov     [rdx], rsi
0x14019a0f3  mov     [rdx+8], rsi
0x14019a0f7  mov     [rdx+10h], rsi
0x14019a0fb  mov     [rdx+18h], rsi
0x14019a0ff  mov     [rdx+20h], rsi
0x14019a103  mov     [rdx+28h], esi
0x14019a106  call    cs:__imp_CoTaskMemAlloc
0x14019a10d  nop     dword ptr [rax+rax+00h]
0x14019a112  lea     ecx, [rsi+1Eh]; cb
0x14019a115  mov     [rbx+30h], rax
0x14019a119  call    cs:__imp_CoTaskMemAlloc
0x14019a120  nop     dword ptr [rax+rax+00h]
0x14019a125  mov     rcx, [rbx+30h]; pv
0x14019a129  mov     [rbx+38h], rax
0x14019a12d  test    rcx, rcx
0x14019a130  jz      short loc_14019A16B
0x14019a132  test    rax, rax
0x14019a135  jz      short loc_14019A16B
0x14019a137  lea     r8, aVirtualMachine_1; "Virtual Machine"
0x14019a13e  lea     edx, [rsi+10h]
0x14019a141  call    cs:__imp__o_wcscpy_s
0x14019a148  nop     dword ptr [rax+rax+00h]
0x14019a14d  mov     rcx, [rbx+38h]
0x14019a151  lea     r8, aVmExdiDriver; "VM EXDI Driver"
0x14019a158  lea     edx, [rsi+0Fh]
0x14019a15b  call    cs:__imp__o_wcscpy_s
0x14019a162  nop     dword ptr [rax+rax+00h]
0x14019a167  mov     edi, esi
0x14019a169  jmp     short loc_14019A1A5
0x14019a16b  mov     edi, 0E082000Eh
0x14019a170  test    rcx, rcx
0x14019a173  jz      short loc_14019A185
0x14019a175  call    cs:__imp_CoTaskMemFree
0x14019a17c  nop     dword ptr [rax+rax+00h]
0x14019a181  mov     [rbx+30h], rsi
0x14019a185  mov     rcx, [rbx+38h]; pv
0x14019a189  test    rcx, rcx
0x14019a18c  jz      short loc_14019A1A5
0x14019a18e  call    cs:__imp_CoTaskMemFree
0x14019a195  nop     dword ptr [rax+rax+00h]
0x14019a19a  mov     [rbx+38h], rsi
0x14019a19e  jmp     short loc_14019A1A5
0x14019a1a0  mov     edi, 0E0820057h
0x14019a1a5  mov     rbx, [rsp+28h+arg_0]
0x14019a1aa  mov     eax, edi
0x14019a1ac  mov     rsi, [rsp+28h+arg_8]
0x14019a1b1  add     rsp, 20h
0x14019a1b5  pop     rdi
0x14019a1b6  retn
```
