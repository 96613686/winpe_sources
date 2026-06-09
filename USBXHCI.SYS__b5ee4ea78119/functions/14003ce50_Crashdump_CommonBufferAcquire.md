# Crashdump_CommonBufferAcquire

- ea: `0x14003ce50`
- end: `0x14003cfa0`
- name: `Crashdump_CommonBufferAcquire`
- size: `336`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140052940`
- `0x140053af4`
- `0x140054410`
- `0x1400556c8`

## callees

- `0x140006438`
- `0x14003ce50`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14003ce86`
- `ntoskrnl!DbgPrintEx` at `0x14003cf8d`
- `ntoskrnl!DbgPrintEx` at `0x14003ce86`
- `ntoskrnl!DbgPrintEx` at `0x14003cf8d`

## string_xrefs

- `0x14003cf34`: `XHCIDUMP: CommonBuffer: %4u (0x%04X) bytes acquired, virtual: 0x%p, logical: 0x%I64X\n`
- `0x14003ce75`: `XHCIDUMP: Crashdump_CommonBufferAcquire: Required Size: %4u\n`

## pseudocode

```c
__int64 __fastcall Crashdump_CommonBufferAcquire(__int64 a1, int a2, __int64 a3)
{
  unsigned int v4; // edi
  _DWORD *v7; // r14
  _DWORD *v8; // rsi
  _DWORD *v9; // r15
  __int64 *v10; // rdx
  _QWORD *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx

  v4 = (a2 + 63) & 0xFFFFFFC0;
  if ( v4 > 0x1000 )
  {
    DbgPrintEx(0x93u, 1u, "XHCIDUMP: Crashdump_CommonBufferAcquire: Required Size: %4u\n", v4);
    return 3221225626LL;
  }
  v7 = (_DWORD *)(a1 + 516);
  v8 = (_DWORD *)(a1 + 520);
  if ( *(_DWORD *)(a1 + 516) )
  {
    if ( v4 <= ((4096 - (*v8 & 0xFFF)) & (unsigned int)-((*v8 & 0xFFF) != 0)) )
    {
      v10 = (__int64 *)(a1 + 496);
      v9 = (_DWORD *)(a1 + 516);
      goto LABEL_13;
    }
    v9 = (_DWORD *)(a1 + 516);
  }
  else
  {
    v9 = (_DWORD *)(a1 + 516);
  }
  v11 = (_QWORD *)CommonBuffer_AcquireBuffer(*(PVOID *)(a1 + 488));
  if ( !v11 )
    return 3221225626LL;
  v10 = (__int64 *)(a1 + 496);
  v12 = *(_QWORD *)(a1 + 496);
  if ( *(_QWORD *)(v12 + 8) != a1 + 496 )
    __fastfail(3u);
  *v11 = v12;
  v11[1] = v10;
  *(_QWORD *)(v12 + 8) = v11;
  *v10 = (__int64)v11;
  ++*(_DWORD *)(a1 + 512);
  *v8 = 0;
LABEL_13:
  v13 = *v10;
  *(_DWORD *)(a3 + 16) = v4;
  v14 = *(_QWORD *)(v13 + 16);
  *(_QWORD *)(a3 + 8) = v14;
  *(_QWORD *)(a3 + 8) = v14 + (unsigned int)*v8;
  v15 = *(_QWORD *)(v13 + 24);
  *(_QWORD *)a3 = v15;
  *(_QWORD *)a3 = v15 + (unsigned int)*v8;
  LODWORD(v15) = *v9;
  *v8 += v4;
  *v7 = v4 + v15;
  DbgPrintEx(
    0x93u,
    3u,
    "XHCIDUMP: CommonBuffer: %4u (0x%04X) bytes acquired, virtual: 0x%p, logical: 0x%I64X\n",
    v4,
    v4,
    *(const void **)(a3 + 8),
    *(_QWORD *)a3);
  return 0;
}

```

## disassembly

```asm
0x14003ce50  push    rbx
0x14003ce52  push    rbp
0x14003ce53  push    rsi
0x14003ce54  push    rdi
0x14003ce55  push    r14
0x14003ce57  push    r15
0x14003ce59  sub     rsp, 48h
0x14003ce5d  lea     edi, [rdx+3Fh]
0x14003ce60  mov     rbp, r8
0x14003ce63  and     edi, 0FFFFFFC0h
0x14003ce66  mov     edx, 1000h
0x14003ce6b  mov     rbx, rcx
0x14003ce6e  cmp     edi, edx
0x14003ce70  jbe     short loc_14003CEA5
0x14003ce72  mov     r9d, edi
0x14003ce75  lea     r8, aXhcidumpCrashd_44; "XHCIDUMP: Crashdump_CommonBufferAcquire"...
0x14003ce7c  mov     edx, 1; Level
0x14003ce81  mov     ecx, 93h; ComponentId
0x14003ce86  call    cs:__imp_DbgPrintEx
0x14003ce8d  nop     dword ptr [rax+rax+00h]
0x14003ce92  mov     eax, 0C000009Ah
0x14003ce97  add     rsp, 48h
0x14003ce9b  pop     r15
0x14003ce9d  pop     r14
0x14003ce9f  pop     rdi
0x14003cea0  pop     rsi
0x14003cea1  pop     rbp
0x14003cea2  pop     rbx
0x14003cea3  retn
0x14003cea5  lea     r14, [rcx+204h]
0x14003ceac  cmp     dword ptr [r14], 0
0x14003ceb0  lea     rsi, [rcx+208h]
0x14003ceb7  jz      short loc_14003CEE3
0x14003ceb9  mov     eax, [rsi]
0x14003cebb  mov     ecx, edx
0x14003cebd  and     eax, 0FFFh
0x14003cec2  sub     ecx, eax
0x14003cec4  neg     eax
0x14003cec6  sbb     eax, eax
0x14003cec8  and     eax, ecx
0x14003ceca  cmp     edi, eax
0x14003cecc  jbe     short loc_14003CED7
0x14003cece  lea     r15, [rbx+204h]
0x14003ced5  jmp     short loc_14003CEE6
0x14003ced7  lea     rdx, [rbx+1F0h]
0x14003cede  mov     r15, r14
0x14003cee1  jmp     short loc_14003CF31
0x14003cee3  mov     r15, r14
0x14003cee6  mov     rcx, [rbx+1E8h]; Context
0x14003ceed  mov     r9d, 31706D44h
0x14003cef3  mov     r8, rbx
0x14003cef6  call    CommonBuffer_AcquireBuffer
0x14003cefb  test    rax, rax
0x14003cefe  jz      short loc_14003CE92
0x14003cf00  lea     rdx, [rbx+1F0h]
0x14003cf07  mov     rcx, [rdx]
0x14003cf0a  cmp     [rcx+8], rdx
0x14003cf0e  jz      short loc_14003CF17
0x14003cf10  mov     ecx, 3
0x14003cf15  int     29h; Win8: RtlFailFast(ecx)
0x14003cf17  mov     [rax], rcx
0x14003cf1a  mov     [rax+8], rdx
0x14003cf1e  mov     [rcx+8], rax
0x14003cf22  mov     [rdx], rax
0x14003cf25  inc     dword ptr [rbx+200h]
0x14003cf2b  mov     dword ptr [rsi], 0
0x14003cf31  mov     rdx, [rdx]
0x14003cf34  lea     r8, aXhcidumpCommon; "XHCIDUMP: CommonBuffer: %4u (0x%04X) by"...
0x14003cf3b  mov     [rbp+10h], edi
0x14003cf3e  mov     r9d, edi
0x14003cf41  mov     rcx, [rdx+10h]
0x14003cf45  mov     [rbp+8], rcx
0x14003cf49  mov     eax, [rsi]
0x14003cf4b  add     rax, rcx
0x14003cf4e  mov     [rbp+8], rax
0x14003cf52  mov     rcx, [rdx+18h]
0x14003cf56  mov     edx, 3; Level
0x14003cf5b  mov     [rbp+0], rcx
0x14003cf5f  mov     eax, [rsi]
0x14003cf61  add     rax, rcx
0x14003cf64  mov     [rbp+0], rax
0x14003cf68  mov     ecx, [r15]
0x14003cf6b  add     [rsi], edi
0x14003cf6d  add     ecx, edi
0x14003cf6f  mov     [r14], ecx
0x14003cf72  mov     ecx, 93h; ComponentId
0x14003cf77  mov     rax, [rbp+0]
0x14003cf7b  mov     [rsp+78h+var_48], rax
0x14003cf80  mov     rax, [rbp+8]
0x14003cf84  mov     [rsp+78h+var_50], rax
0x14003cf89  mov     [rsp+78h+var_58], edi
0x14003cf8d  call    cs:__imp_DbgPrintEx
0x14003cf94  nop     dword ptr [rax+rax+00h]
0x14003cf99  xor     eax, eax
0x14003cf9b  jmp     loc_14003CE97
```
