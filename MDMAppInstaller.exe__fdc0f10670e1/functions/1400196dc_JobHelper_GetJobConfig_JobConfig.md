# JobHelper::GetJobConfig(_JobConfig &)

- ea: `0x1400196dc`
- end: `0x140019749`
- name: `?GetJobConfig@JobHelper@@SAJAEAU_JobConfig@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(struct _JobConfig *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000d898`
- `0x140010a2c`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x14001a8d0`

## pseudocode

```c
__int64 __fastcall JobHelper::GetJobConfig(struct _JobConfig *a1)
{
  _QWORD v3[4]; // [rsp+20h] [rbp-38h] BYREF

  std::wstring::wstring((__int64)v3, (__int64)&word_14001E5B4);
  *((_DWORD *)a1 + 1) = 0;
  *((_DWORD *)a1 + 2) = 600;
  *((_BYTE *)a1 + 12) = 1;
  *(_DWORD *)a1 = 0;
  *((_QWORD *)a1 + 2) = 30;
  std::wstring::_Tidy(v3, 1, 0);
  return 0;
}

```

## disassembly

```asm
0x1400196dc  push    rbx
0x1400196de  sub     rsp, 50h
0x1400196e2  mov     rax, cs:__security_cookie
0x1400196e9  xor     rax, rsp
0x1400196ec  mov     [rsp+58h+var_18], rax
0x1400196f1  mov     rbx, rcx
0x1400196f4  lea     rdx, word_14001E5B4
0x1400196fb  lea     rcx, [rsp+58h+var_38]
0x140019700  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140019705  xor     r8d, r8d
0x140019708  mov     dword ptr [rbx+4], 0
0x14001970f  mov     dl, 1
0x140019711  mov     dword ptr [rbx+8], 258h
0x140019718  lea     rcx, [rsp+58h+var_38]
0x14001971d  mov     byte ptr [rbx+0Ch], 1
0x140019721  mov     dword ptr [rbx], 0
0x140019727  mov     qword ptr [rbx+10h], 1Eh
0x14001972f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140019734  xor     eax, eax
0x140019736  mov     rcx, [rsp+58h+var_18]
0x14001973b  xor     rcx, rsp; StackCookie
0x14001973e  call    __security_check_cookie
0x140019743  add     rsp, 50h
0x140019747  pop     rbx
0x140019748  retn
```
