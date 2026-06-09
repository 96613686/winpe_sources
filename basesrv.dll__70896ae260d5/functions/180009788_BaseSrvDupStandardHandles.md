# BaseSrvDupStandardHandles

- ea: `0x180009788`
- end: `0x1800099a5`
- name: `BaseSrvDupStandardHandles`
- size: `541`
- prototype: `NTSTATUS __fastcall(HANDLE SourceProcessHandle, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008644`
- `0x18000c088`

## callees

- `0x180009788`

## import_xrefs

- `ntdll!NtDuplicateObject` at `0x18000982f`
- `ntdll!NtDuplicateObject` at `0x18000986a`
- `ntdll!NtDuplicateObject` at `0x18000989f`
- `ntdll!NtDuplicateObject` at `0x1800098e7`
- `ntdll!NtDuplicateObject` at `0x180009920`
- `ntdll!NtDuplicateObject` at `0x180009958`
- `ntdll!NtDuplicateObject` at `0x18000982f`
- `ntdll!NtDuplicateObject` at `0x18000986a`
- `ntdll!NtDuplicateObject` at `0x18000989f`
- `ntdll!NtDuplicateObject` at `0x1800098e7`
- `ntdll!NtDuplicateObject` at `0x180009920`
- `ntdll!NtDuplicateObject` at `0x180009958`

## pseudocode

```c
NTSTATUS __fastcall BaseSrvDupStandardHandles(HANDLE SourceProcessHandle, __int64 a2)
{
  __int64 v2; // rbx
  HANDLE v3; // r13
  HANDLE *v5; // r14
  HANDLE *v6; // rbp
  void *v7; // rdi
  __int64 v8; // r15
  NTSTATUS result; // eax
  void *v10; // r12
  NTSTATUS v11; // ebp
  HANDLE v12; // rdx

  v2 = *(_QWORD *)(a2 + 32);
  v3 = 0;
  v5 = (HANDLE *)(v2 + 16);
  v6 = (HANDLE *)(v2 + 24);
  v7 = *(void **)(v2 + 16);
  v8 = *(_QWORD *)(v2 + 24);
  if ( *(_BYTE *)(v2 + 249) )
    return 0;
  if ( (unsigned __int64)v7 + 6 <= 5
    || (unsigned __int64)(v8 + 6) <= 5
    || (unsigned __int64)(*(_QWORD *)(v2 + 32) + 6LL) <= 5 )
  {
    return -1073741816;
  }
  v10 = *(void **)(*((_QWORD *)NtCurrentTeb()->CsrClientThread + 7) + 80LL);
  if ( !v7 || (result = NtDuplicateObject(v10, v7, SourceProcessHandle, (PHANDLE)(v2 + 16), 0, 2u, 2u), result >= 0) )
  {
    if ( *v6 )
    {
      v3 = *v6;
      v11 = NtDuplicateObject(v10, *v6, SourceProcessHandle, (PHANDLE)(v2 + 24), 0, 2u, 2u);
      if ( v11 < 0 )
      {
        if ( v7 )
        {
          NtDuplicateObject(SourceProcessHandle, *v5, 0, 0, 0, 0, 1u);
          *v5 = v7;
        }
        return v11;
      }
    }
    v12 = *(HANDLE *)(v2 + 32);
    if ( v12 )
    {
      if ( v12 == v3 )
      {
        *(_QWORD *)(v2 + 32) = *(_QWORD *)(v2 + 24);
      }
      else
      {
        v11 = NtDuplicateObject(v10, v12, SourceProcessHandle, (PHANDLE)(v2 + 32), 0, 2u, 2u);
        if ( v11 < 0 )
        {
          if ( v7 )
          {
            NtDuplicateObject(SourceProcessHandle, *(HANDLE *)(v2 + 16), 0, 0, 0, 0, 1u);
            *(_QWORD *)(v2 + 16) = v7;
          }
          if ( v8 )
          {
            NtDuplicateObject(SourceProcessHandle, *(HANDLE *)(v2 + 24), 0, 0, 0, 0, 1u);
            *(_QWORD *)(v2 + 24) = v8;
          }
          return v11;
        }
      }
    }
    *(_BYTE *)(v2 + 249) = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009788  mov     [rsp+arg_0], rbx
0x18000978d  mov     [rsp+arg_8], rbp
0x180009792  mov     [rsp+arg_10], rsi
0x180009797  push    rdi
0x180009798  push    r12
0x18000979a  push    r13
0x18000979c  push    r14
0x18000979e  push    r15
0x1800097a0  sub     rsp, 40h
0x1800097a4  mov     rbx, [rdx+20h]
0x1800097a8  xor     r13d, r13d
0x1800097ab  mov     rsi, rcx
0x1800097ae  lea     r14, [rbx+10h]
0x1800097b2  lea     rbp, [rbx+18h]
0x1800097b6  mov     rdi, [r14]
0x1800097b9  mov     r15, [rbp+0]
0x1800097bd  cmp     [rbx+0F9h], r13b
0x1800097c4  jz      short loc_1800097CD
0x1800097c6  xor     eax, eax
0x1800097c8  jmp     loc_180009986
0x1800097cd  lea     rax, [rdi+6]
0x1800097d1  cmp     rax, 5
0x1800097d5  jbe     loc_180009981
0x1800097db  lea     rax, [r15+6]
0x1800097df  cmp     rax, 5
0x1800097e3  jbe     loc_180009981
0x1800097e9  mov     rax, [rbx+20h]
0x1800097ed  add     rax, 6
0x1800097f1  cmp     rax, 5
0x1800097f5  jbe     loc_180009981
0x1800097fb  mov     rax, gs:70h
0x180009804  mov     rcx, [rax+38h]
0x180009808  mov     eax, 2
0x18000980d  mov     r12, [rcx+50h]
0x180009811  test    rdi, rdi
0x180009814  jz      short loc_180009848
0x180009816  mov     [rsp+68h+Options], eax; Options
0x18000981a  mov     r9, r14; TargetHandle
0x18000981d  mov     [rsp+68h+HandleAttributes], eax; HandleAttributes
0x180009821  mov     r8, rsi; TargetProcessHandle
0x180009824  and     [rsp+68h+DesiredAccess], r13d
0x180009829  mov     rdx, rdi; SourceHandle
0x18000982c  mov     rcx, r12; SourceProcessHandle
0x18000982f  call    cs:__imp_NtDuplicateObject
0x180009836  nop     dword ptr [rax+rax+00h]
0x18000983b  test    eax, eax
0x18000983d  js      loc_180009986
0x180009843  mov     eax, 2
0x180009848  mov     rdx, [rbp+0]; SourceHandle
0x18000984c  test    rdx, rdx
0x18000984f  jz      short loc_1800098B5
0x180009851  mov     [rsp+68h+Options], eax; Options
0x180009855  mov     r9, rbp; TargetHandle
0x180009858  mov     [rsp+68h+HandleAttributes], eax; HandleAttributes
0x18000985c  mov     r8, rsi; TargetProcessHandle
0x18000985f  and     [rsp+68h+DesiredAccess], 0
0x180009864  mov     rcx, r12; SourceProcessHandle
0x180009867  mov     r13, rdx
0x18000986a  call    cs:__imp_NtDuplicateObject
0x180009871  nop     dword ptr [rax+rax+00h]
0x180009876  mov     ebp, eax
0x180009878  test    eax, eax
0x18000987a  jns     short loc_1800098B5
0x18000987c  test    rdi, rdi
0x18000987f  jz      short loc_1800098AE
0x180009881  mov     rdx, [r14]; SourceHandle
0x180009884  xor     r9d, r9d; TargetHandle
0x180009887  mov     [rsp+68h+Options], 1; Options
0x18000988f  xor     r8d, r8d; TargetProcessHandle
0x180009892  and     [rsp+68h+HandleAttributes], 0
0x180009897  mov     rcx, rsi; SourceProcessHandle
0x18000989a  and     [rsp+68h+DesiredAccess], 0
0x18000989f  call    cs:__imp_NtDuplicateObject
0x1800098a6  nop     dword ptr [rax+rax+00h]
0x1800098ab  mov     [r14], rdi
0x1800098ae  mov     eax, ebp
0x1800098b0  jmp     loc_180009986
0x1800098b5  mov     rdx, [rbx+20h]; SourceHandle
0x1800098b9  test    rdx, rdx
0x1800098bc  jz      loc_180009975
0x1800098c2  cmp     rdx, r13
0x1800098c5  jz      loc_18000996D
0x1800098cb  mov     eax, 2
0x1800098d0  lea     r9, [rbx+20h]; TargetHandle
0x1800098d4  mov     [rsp+68h+Options], eax; Options
0x1800098d8  mov     r8, rsi; TargetProcessHandle
0x1800098db  mov     [rsp+68h+HandleAttributes], eax; HandleAttributes
0x1800098df  mov     rcx, r12; SourceProcessHandle
0x1800098e2  and     [rsp+68h+DesiredAccess], 0
0x1800098e7  call    cs:__imp_NtDuplicateObject
0x1800098ee  nop     dword ptr [rax+rax+00h]
0x1800098f3  xor     r14d, r14d
0x1800098f6  mov     ebp, eax
0x1800098f8  test    eax, eax
0x1800098fa  jns     short loc_180009975
0x1800098fc  test    rdi, rdi
0x1800098ff  jz      short loc_180009930
0x180009901  mov     rdx, [rbx+10h]; SourceHandle
0x180009905  xor     r9d, r9d; TargetHandle
0x180009908  mov     [rsp+68h+Options], 1; Options
0x180009910  xor     r8d, r8d; TargetProcessHandle
0x180009913  mov     [rsp+68h+HandleAttributes], r14d; HandleAttributes
0x180009918  mov     rcx, rsi; SourceProcessHandle
0x18000991b  mov     [rsp+68h+DesiredAccess], r14d; DesiredAccess
0x180009920  call    cs:__imp_NtDuplicateObject
0x180009927  nop     dword ptr [rax+rax+00h]
0x18000992c  mov     [rbx+10h], rdi
0x180009930  test    r15, r15
0x180009933  jz      loc_1800098AE
0x180009939  mov     rdx, [rbx+18h]; SourceHandle
0x18000993d  xor     r9d, r9d; TargetHandle
0x180009940  mov     [rsp+68h+Options], 1; Options
0x180009948  xor     r8d, r8d; TargetProcessHandle
0x18000994b  mov     [rsp+68h+HandleAttributes], r14d; HandleAttributes
0x180009950  mov     rcx, rsi; SourceProcessHandle
0x180009953  mov     [rsp+68h+DesiredAccess], r14d; DesiredAccess
0x180009958  call    cs:__imp_NtDuplicateObject
0x18000995f  nop     dword ptr [rax+rax+00h]
0x180009964  mov     [rbx+18h], r15
0x180009968  jmp     loc_1800098AE
0x18000996d  mov     rax, [rbx+18h]
0x180009971  mov     [rbx+20h], rax
0x180009975  mov     byte ptr [rbx+0F9h], 1
0x18000997c  jmp     loc_1800097C6
0x180009981  mov     eax, 0C0000008h
0x180009986  lea     r11, [rsp+68h+var_28]
0x18000998b  mov     rbx, [r11+30h]
0x18000998f  mov     rbp, [r11+38h]
0x180009993  mov     rsi, [r11+40h]
0x180009997  mov     rsp, r11
0x18000999a  pop     r15
0x18000999c  pop     r14
0x18000999e  pop     r13
0x1800099a0  pop     r12
0x1800099a2  pop     rdi
0x1800099a3  retn
```
