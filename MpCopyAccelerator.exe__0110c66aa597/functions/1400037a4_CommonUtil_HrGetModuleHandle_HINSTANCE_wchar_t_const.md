# CommonUtil::HrGetModuleHandle(HINSTANCE__ * *,wchar_t const *)

- ea: `0x1400037a4`
- end: `0x140003812`
- name: `?HrGetModuleHandle@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEB_W@Z`
- size: `110`
- prototype: `int(CommonUtil *__hidden this, HINSTANCE *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003414`

## callees

- `0x1400037a4`
- `0x14000493c`
- `0x140020220`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1400037b7`
- `KERNEL32!GetModuleHandleW` at `0x1400037b7`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrGetModuleHandle(CommonUtil *this, HINSTANCE *a2, const wchar_t *a3)
{
  int v4; // edi
  HMODULE ModuleHandleW; // rax
  __int64 v6; // rcx
  unsigned int LastFailure; // ebx

  v4 = (int)a2;
  ModuleHandleW = GetModuleHandleW((LPCWSTR)a2);
  *(_QWORD *)this = ModuleHandleW;
  if ( ModuleHandleW )
    return 0;
  LastFailure = HrGetLastFailure(v6);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)WPP_b1ecc9abb7cc30bcf0685ece08501d8e_Traceguids,
      v4,
      LastFailure);
  return LastFailure;
}

```

## disassembly

```asm
0x1400037a4  mov     [rsp+arg_0], rbx
0x1400037a9  push    rdi
0x1400037aa  sub     rsp, 30h
0x1400037ae  mov     rbx, rcx
0x1400037b1  mov     rdi, rdx
0x1400037b4  mov     rcx, rdx; lpModuleName
0x1400037b7  call    cs:__imp_GetModuleHandleW
0x1400037bd  mov     [rbx], rax
0x1400037c0  test    rax, rax
0x1400037c3  jnz     short loc_140003805
0x1400037c5  call    HrGetLastFailure
0x1400037ca  mov     ebx, eax
0x1400037cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400037d3  lea     rax, WPP_GLOBAL_Control
0x1400037da  cmp     rcx, rax
0x1400037dd  jz      short loc_140003801
0x1400037df  test    byte ptr [rcx+1Ch], 1
0x1400037e3  jz      short loc_140003801
0x1400037e5  mov     rcx, [rcx+10h]
0x1400037e9  lea     r8, WPP_b1ecc9abb7cc30bcf0685ece08501d8e_Traceguids
0x1400037f0  mov     edx, 14h
0x1400037f5  mov     [rsp+38h+var_18], ebx
0x1400037f9  mov     r9, rdi
0x1400037fc  call    WPP_SF_Sd
0x140003801  mov     eax, ebx
0x140003803  jmp     short loc_140003807
0x140003805  xor     eax, eax
0x140003807  mov     rbx, [rsp+38h+arg_0]
0x14000380c  add     rsp, 30h
0x140003810  pop     rdi
0x140003811  retn
```
