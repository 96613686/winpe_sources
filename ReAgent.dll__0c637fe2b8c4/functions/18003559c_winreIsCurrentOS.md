# winreIsCurrentOS

- ea: `0x18003559c`
- end: `0x1800356cc`
- name: `winreIsCurrentOS`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800193e8`

## callees

- `0x1800059fc`
- `0x180033864`
- `0x18003559c`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180035694`
- `ntdll!RtlNtStatusToDosError` at `0x180035694`
- `bcd!BcdCloseStore` at `0x180035683`
- `bcd!BcdCloseStore` at `0x180035683`
- `bcd!BcdOpenStore` at `0x1800355f3`
- `bcd!BcdOpenStore` at `0x1800355f3`

## string_xrefs

- `0x18003562a`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x180035602`: `Open store failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreIsCurrentOS(_QWORD *a1, _DWORD *a2)
{
  ULONG v4; // ebx
  int v5; // eax
  NTSTATUS IdForCurrentOS; // edi
  __int64 v7; // rcx
  void *v9; // [rsp+30h] [rbp-48h] BYREF
  struct _GUID v10; // [rsp+38h] [rbp-40h] BYREF

  v9 = 0;
  v10 = 0;
  if ( !a2 )
  {
    v4 = 87;
LABEL_16:
    UnattendLogW(1, L"Failed to check whether it's current OS GUID: 0x%x", v4);
    return v4;
  }
  v4 = 0;
  if ( a1 )
  {
    v5 = BcdOpenStore(0, 0, &v9);
    IdForCurrentOS = v5;
    if ( v5 >= 0 )
    {
      IdForCurrentOS = winreGetIdForCurrentOS(v9, &v10);
      if ( IdForCurrentOS >= 0 )
      {
        v7 = *(_QWORD *)&v10.Data1 - *a1;
        if ( *(_QWORD *)&v10.Data1 == *a1 )
          v7 = *(_QWORD *)v10.Data4 - a1[1];
        *a2 = v7 == 0;
      }
      else
      {
        UnattendLogW(
          2,
          L"winreIsCurrentOS %s (0x%x) in file %S line %d",
          L"failed to get id for current os",
          (unsigned int)IdForCurrentOS,
          "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
          3049);
      }
    }
    else
    {
      UnattendLogW(1, L"Open store failed: 0x%x", (unsigned int)v5);
    }
    if ( v9 )
    {
      BcdCloseStore(v9);
      v9 = 0;
    }
    if ( IdForCurrentOS < 0 )
    {
      v4 = RtlNtStatusToDosError(IdForCurrentOS);
      if ( v4 )
        goto LABEL_16;
    }
  }
  else
  {
    *a2 = 1;
  }
  return v4;
}

```

## disassembly

```asm
0x18003559c  push    rbx
0x18003559e  push    rbp
0x18003559f  push    rsi
0x1800355a0  push    rdi
0x1800355a1  sub     rsp, 58h
0x1800355a5  mov     rax, cs:__security_cookie
0x1800355ac  xor     rax, rsp
0x1800355af  mov     [rsp+78h+var_30], rax
0x1800355b4  mov     [rsp+78h+var_48], 0
0x1800355bd  xorps   xmm0, xmm0
0x1800355c0  mov     rsi, rdx
0x1800355c3  mov     rbp, rcx
0x1800355c6  movups  xmmword ptr [rsp+78h+var_40.Data1], xmm0
0x1800355cb  test    rdx, rdx
0x1800355ce  jnz     short loc_1800355D8
0x1800355d0  lea     ebx, [rdx+57h]
0x1800355d3  jmp     loc_1800356A0
0x1800355d8  xor     ebx, ebx
0x1800355da  test    rbp, rbp
0x1800355dd  jnz     short loc_1800355EA
0x1800355df  mov     dword ptr [rdx], 1
0x1800355e5  jmp     loc_1800356B4
0x1800355ea  lea     r8, [rsp+78h+var_48]
0x1800355ef  xor     edx, edx
0x1800355f1  xor     ecx, ecx
0x1800355f3  call    cs:__imp_BcdOpenStore
0x1800355f9  mov     edi, eax
0x1800355fb  test    eax, eax
0x1800355fd  jns     short loc_180035615
0x1800355ff  mov     r8d, eax
0x180035602  lea     rdx, aOpenStoreFaile; "Open store failed: 0x%x"
0x180035609  mov     ecx, 1
0x18003560e  call    UnattendLogW
0x180035613  jmp     short loc_180035679
0x180035615  mov     rcx, [rsp+78h+var_48]; void *
0x18003561a  lea     rdx, [rsp+78h+var_40]; struct _GUID *
0x18003561f  call    ?winreGetIdForCurrentOS@@YAJPEAXPEAU_GUID@@@Z; winreGetIdForCurrentOS(void *,_GUID *)
0x180035624  mov     edi, eax
0x180035626  test    eax, eax
0x180035628  jns     short loc_18003565B
0x18003562a  lea     rax, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180035631  mov     [rsp+78h+var_50], 0BE9h
0x180035639  mov     r9d, edi
0x18003563c  mov     [rsp+78h+var_58], rax
0x180035641  lea     r8, aFailedToGetIdF; "failed to get id for current os"
0x180035648  mov     ecx, 2
0x18003564d  lea     rdx, aWinreiscurrent; "winreIsCurrentOS %s (0x%x) in file %S l"...
0x180035654  call    UnattendLogW
0x180035659  jmp     short loc_180035679
0x18003565b  mov     rcx, qword ptr [rsp+78h+var_40.Data1]
0x180035660  sub     rcx, [rbp+0]
0x180035664  jnz     short loc_18003566F
0x180035666  mov     rcx, qword ptr [rsp+78h+var_40.Data4]
0x18003566b  sub     rcx, [rbp+8]
0x18003566f  xor     eax, eax
0x180035671  test    rcx, rcx
0x180035674  setz    al
0x180035677  mov     [rsi], eax
0x180035679  mov     rcx, [rsp+78h+var_48]
0x18003567e  test    rcx, rcx
0x180035681  jz      short loc_18003568E
0x180035683  call    cs:__imp_BcdCloseStore
0x180035689  mov     [rsp+78h+var_48], rbx
0x18003568e  test    edi, edi
0x180035690  jns     short loc_1800356B4
0x180035692  mov     ecx, edi; Status
0x180035694  call    cs:__imp_RtlNtStatusToDosError
0x18003569a  mov     ebx, eax
0x18003569c  test    eax, eax
0x18003569e  jz      short loc_1800356B4
0x1800356a0  mov     r8d, ebx
0x1800356a3  lea     rdx, aFailedToCheckW_0; "Failed to check whether it's current OS"...
0x1800356aa  mov     ecx, 1
0x1800356af  call    UnattendLogW
0x1800356b4  mov     eax, ebx
0x1800356b6  mov     rcx, [rsp+78h+var_30]
0x1800356bb  xor     rcx, rsp; StackCookie
0x1800356be  call    __security_check_cookie
0x1800356c3  add     rsp, 58h
0x1800356c7  pop     rdi
0x1800356c8  pop     rsi
0x1800356c9  pop     rbp
0x1800356ca  pop     rbx
0x1800356cb  retn
```
