# CNetworkItemFactory::s_GetFIPriority(IFunctionInstance *)

- ea: `0x18000568c`
- end: `0x180005739`
- name: `?s_GetFIPriority@CNetworkItemFactory@@SAHPEAUIFunctionInstance@@@Z`
- size: `173`
- prototype: `__int64 __fastcall(struct IFunctionInstance *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002ab8`
- `0x18000488c`

## callees

- `0x18000568c`
- `0x18000b010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1800056d8`
- `KERNEL32!CompareStringW` at `0x18000570a`
- `KERNEL32!CompareStringW` at `0x1800056d8`
- `KERNEL32!CompareStringW` at `0x18000570a`
- `ole32!CoTaskMemFree` at `0x180005720`
- `ole32!CoTaskMemFree` at `0x18000572b`
- `ole32!CoTaskMemFree` at `0x180005720`
- `ole32!CoTaskMemFree` at `0x18000572b`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::s_GetFIPriority(struct IFunctionInstance *a1)
{
  struct IFunctionInstanceVtbl *lpVtbl; // rax
  unsigned int v2; // ebx
  PCNZWCH lpString1; // [rsp+40h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF

  lpVtbl = a1->lpVtbl;
  v2 = 0;
  lpString1 = 0;
  pv = 0;
  if ( ((int (__fastcall *)(struct IFunctionInstance *, PCNZWCH *, LPVOID *))lpVtbl->GetCategory)(a1, &lpString1, &pv) >= 0 )
  {
    if ( CompareStringW(0x7Fu, 0, lpString1, -1, L"Provider\\Microsoft.Networking.WSD", -1) == 2 )
    {
      v2 = 10;
    }
    else if ( CompareStringW(0x7Fu, 0, lpString1, -1, L"Provider\\Microsoft.Networking.Netbios", -1) == 2 )
    {
      v2 = 9;
    }
    CoTaskMemFree((LPVOID)lpString1);
    CoTaskMemFree(pv);
  }
  return v2;
}

```

## disassembly

```asm
0x18000568c  mov     r11, rsp
0x18000568f  push    rbx
0x180005690  sub     rsp, 30h
0x180005694  mov     rax, [rcx]
0x180005697  lea     r8, [r11+10h]
0x18000569b  xor     ebx, ebx
0x18000569d  lea     rdx, [r11+8]
0x1800056a1  mov     [r11+8], rbx
0x1800056a5  mov     [r11+10h], rbx
0x1800056a9  mov     rax, [rax+38h]
0x1800056ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056b2  test    eax, eax
0x1800056b4  js      short loc_180005731
0x1800056b6  mov     r8, [rsp+38h+lpString1]; lpString1
0x1800056bb  lea     rax, aProviderMicros_1; "Provider\\Microsoft.Networking.WSD"
0x1800056c2  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800056ca  lea     ecx, [rbx+7Fh]; Locale
0x1800056cd  or      r9d, 0FFFFFFFFh; cchCount1
0x1800056d1  mov     [rsp+38h+lpString2], rax; lpString2
0x1800056d6  xor     edx, edx; dwCmpFlags
0x1800056d8  call    cs:__imp_CompareStringW
0x1800056de  cmp     eax, 2
0x1800056e1  jnz     short loc_1800056E8
0x1800056e3  lea     ebx, [rax+8]
0x1800056e6  jmp     short loc_18000571B
0x1800056e8  mov     r8, [rsp+38h+lpString1]; lpString1
0x1800056ed  lea     rax, aProviderMicros_0; "Provider\\Microsoft.Networking.Netbios"
0x1800056f4  xor     edx, edx; dwCmpFlags
0x1800056f6  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800056fe  or      r9d, 0FFFFFFFFh; cchCount1
0x180005702  mov     [rsp+38h+lpString2], rax; lpString2
0x180005707  lea     ecx, [rdx+7Fh]; Locale
0x18000570a  call    cs:__imp_CompareStringW
0x180005710  cmp     eax, 2
0x180005713  mov     eax, 9
0x180005718  cmovz   ebx, eax
0x18000571b  mov     rcx, [rsp+38h+lpString1]; pv
0x180005720  call    cs:__imp_CoTaskMemFree
0x180005726  mov     rcx, [rsp+38h+pv]; pv
0x18000572b  call    cs:__imp_CoTaskMemFree
0x180005731  mov     eax, ebx
0x180005733  add     rsp, 30h
0x180005737  pop     rbx
0x180005738  retn
```
