# winreGetIdForCurrentOS(void *,_GUID *)

- ea: `0x180033864`
- end: `0x1800338f6`
- name: `?winreGetIdForCurrentOS@@YAJPEAXPEAU_GUID@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(void *, struct _GUID *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18003559c`
- `0x180035b0c`
- `0x180035c90`
- `0x180035e88`

## callees

- `0x1800059fc`
- `0x180033864`
- `0x18005cf30`

## import_xrefs

- `bcd!BcdCloseObject` at `0x1800338d6`
- `bcd!BcdCloseObject` at `0x1800338d6`
- `bcd!BcdQueryObject` at `0x1800338c4`
- `bcd!BcdQueryObject` at `0x1800338c4`
- `bcd!BcdOpenObject` at `0x180033895`
- `bcd!BcdOpenObject` at `0x180033895`

## string_xrefs

- `0x1800338a4`: `BcdOpenObject failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreGetIdForCurrentOS(void *a1, struct _GUID *a2)
{
  int v3; // eax
  unsigned int Object; // ebx
  __int64 v6; // [rsp+20h] [rbp-18h] BYREF

  v6 = 0;
  v3 = BcdOpenObject(a1, &GUID_CURRENT_BOOT_ENTRY, &v6);
  Object = v3;
  if ( v3 >= 0 )
    Object = BcdQueryObject(v6, 0, 0, a2);
  else
    UnattendLogW(1, L"BcdOpenObject failed: 0x%x", (unsigned int)v3);
  if ( v6 )
    BcdCloseObject();
  return Object;
}

```

## disassembly

```asm
0x180033864  mov     [rsp+arg_10], rbx
0x180033869  push    rdi
0x18003386a  sub     rsp, 30h
0x18003386e  mov     rax, cs:__security_cookie
0x180033875  xor     rax, rsp
0x180033878  mov     [rsp+38h+var_10], rax
0x18003387d  mov     rdi, rdx
0x180033880  mov     [rsp+38h+var_18], 0
0x180033889  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x180033890  lea     r8, [rsp+38h+var_18]
0x180033895  call    cs:__imp_BcdOpenObject
0x18003389b  mov     ebx, eax
0x18003389d  test    eax, eax
0x18003389f  jns     short loc_1800338B7
0x1800338a1  mov     r8d, eax
0x1800338a4  lea     rdx, aBcdopenobjectF_0; "BcdOpenObject failed: 0x%x"
0x1800338ab  mov     ecx, 1
0x1800338b0  call    UnattendLogW
0x1800338b5  jmp     short loc_1800338CC
0x1800338b7  mov     rcx, [rsp+38h+var_18]
0x1800338bc  mov     r9, rdi
0x1800338bf  xor     r8d, r8d
0x1800338c2  xor     edx, edx
0x1800338c4  call    cs:__imp_BcdQueryObject
0x1800338ca  mov     ebx, eax
0x1800338cc  mov     rcx, [rsp+38h+var_18]
0x1800338d1  test    rcx, rcx
0x1800338d4  jz      short loc_1800338DC
0x1800338d6  call    cs:__imp_BcdCloseObject
0x1800338dc  mov     eax, ebx
0x1800338de  mov     rcx, [rsp+38h+var_10]
0x1800338e3  xor     rcx, rsp; StackCookie
0x1800338e6  call    __security_check_cookie
0x1800338eb  mov     rbx, [rsp+38h+arg_10]
0x1800338f0  add     rsp, 30h
0x1800338f4  pop     rdi
0x1800338f5  retn
```
