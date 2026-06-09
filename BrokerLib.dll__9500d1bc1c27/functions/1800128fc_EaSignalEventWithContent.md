# EaSignalEventWithContent

- ea: `0x1800128fc`
- end: `0x1800129f7`
- name: `EaSignalEventWithContent`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18001a898`

## callees

- `0x1800128fc`
- `0x180012a00`
- `0x180015af0`
- `0x18001a940`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800129d7`
- `ntdll!RtlFreeHeap` at `0x1800129d7`
- `ntdll!ZwUpdateWnfStateData` at `0x1800129a9`
- `ntdll!ZwUpdateWnfStateData` at `0x1800129a9`

## pseudocode

```c
__int64 __fastcall EaSignalEventWithContent(__int64 a1, __int64 a2, char a3, __int64 a4, unsigned int *a5)
{
  bool v5; // zf
  int v6; // ebx
  PVOID *p_P; // rcx
  int updated; // eax
  unsigned int v10; // [rsp+40h] [rbp-28h] BYREF
  PVOID P; // [rsp+48h] [rbp-20h] BYREF
  __int64 v12; // [rsp+50h] [rbp-18h] BYREF

  v5 = *(_QWORD *)(a4 + 16) == 0;
  v12 = a1;
  P = 0;
  v10 = 0;
  if ( v5 || a5 )
  {
    p_P = &P;
    LOBYTE(p_P) = a2;
    LOBYTE(a2) = a3;
    v6 = EaSignalPrepareEventForPublishing(p_P, a2, a4, &v10, &P);
    if ( v6 >= 0 )
    {
      if ( v10 <= 0x1000 )
      {
        if ( a5 )
          updated = EaSignalPublishSynchronous(&v12, P, v10, *a5);
        else
          updated = ZwUpdateWnfStateData(&v12, P, v10, 0, 0, 0, 0);
        v6 = updated;
      }
      else
      {
        v6 = -2147483643;
      }
    }
    if ( P )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800128fc  mov     [rsp+arg_8], rbx
0x180012901  push    rsi
0x180012902  sub     rsp, 60h
0x180012906  mov     rax, cs:__security_cookie
0x18001290d  xor     rax, rsp
0x180012910  mov     [rsp+68h+var_10], rax
0x180012915  cmp     qword ptr [r9+10h], 0
0x18001291a  mov     rax, r9
0x18001291d  mov     rsi, [rsp+68h+arg_20]
0x180012925  mov     r10b, r8b
0x180012928  mov     r11b, dl
0x18001292b  mov     [rsp+68h+var_18], rcx
0x180012930  mov     [rsp+68h+P], 0
0x180012939  mov     [rsp+68h+var_28], 0
0x180012941  jz      short loc_180012952
0x180012943  test    rsi, rsi
0x180012946  jnz     short loc_180012952
0x180012948  mov     ebx, 0C000000Dh
0x18001294d  jmp     loc_1800129DD
0x180012952  lea     rcx, [rsp+68h+P]
0x180012957  mov     r8, rax
0x18001295a  mov     [rsp+68h+var_48], rcx
0x18001295f  lea     r9, [rsp+68h+var_28]
0x180012964  mov     cl, r11b
0x180012967  mov     dl, r10b
0x18001296a  call    EaSignalPrepareEventForPublishing
0x18001296f  mov     ebx, eax
0x180012971  test    eax, eax
0x180012973  js      short loc_1800129BB
0x180012975  mov     r8d, [rsp+68h+var_28]
0x18001297a  cmp     r8d, 1000h
0x180012981  jbe     short loc_18001298A
0x180012983  mov     ebx, 80000005h
0x180012988  jmp     short loc_1800129BB
0x18001298a  mov     rdx, [rsp+68h+P]
0x18001298f  lea     rcx, [rsp+68h+var_18]
0x180012994  test    rsi, rsi
0x180012997  jnz     short loc_1800129B1
0x180012999  mov     [rsp+68h+var_38], esi
0x18001299d  xor     r9d, r9d
0x1800129a0  mov     [rsp+68h+var_40], esi
0x1800129a4  mov     [rsp+68h+var_48], rsi
0x1800129a9  call    cs:__imp_ZwUpdateWnfStateData
0x1800129af  jmp     short loc_1800129B9
0x1800129b1  mov     r9d, [rsi]
0x1800129b4  call    EaSignalPublishSynchronous
0x1800129b9  mov     ebx, eax
0x1800129bb  cmp     [rsp+68h+P], 0
0x1800129c1  jz      short loc_1800129DD
0x1800129c3  mov     rcx, gs:60h
0x1800129cc  xor     edx, edx; Flags
0x1800129ce  mov     r8, [rsp+68h+P]; P
0x1800129d3  mov     rcx, [rcx+30h]; HeapHandle
0x1800129d7  call    cs:__imp_RtlFreeHeap
0x1800129dd  mov     eax, ebx
0x1800129df  mov     rcx, [rsp+68h+var_10]
0x1800129e4  xor     rcx, rsp; StackCookie
0x1800129e7  call    __security_check_cookie
0x1800129ec  mov     rbx, [rsp+68h+arg_8]
0x1800129f1  add     rsp, 60h
0x1800129f5  pop     rsi
0x1800129f6  retn
```
