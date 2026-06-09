# _DllEntryPoint

- ea: `0x1800255f0`
- end: `0x18002564f`
- name: `_DllEntryPoint`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180018ae0`

## callees

- `0x1800255f0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180025602`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180025602`

## pseudocode

```c
__int64 __fastcall DllEntryPoint(HMODULE a1, int a2)
{
  void (__fastcall *v3)(__int64, _QWORD); // rax
  __int64 v4; // rcx

  if ( a2 )
  {
    if ( a2 == 1 )
    {
      DisableThreadLibraryCalls(a1);
      v3 = (void (__fastcall *)(__int64, _QWORD))qword_1800AC018;
      g_hInst = a1;
      if ( qword_1800AC018 )
      {
        v4 = 1;
LABEL_7:
        v3(v4, off_1800AC008);
      }
    }
  }
  else
  {
    v3 = (void (__fastcall *)(__int64, _QWORD))qword_1800AC018;
    if ( qword_1800AC018 )
    {
      v4 = 0;
      goto LABEL_7;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800255f0  push    rbx
0x1800255f2  sub     rsp, 20h
0x1800255f6  mov     rbx, rcx
0x1800255f9  test    edx, edx
0x1800255fb  jz      short loc_180025628
0x1800255fd  cmp     edx, 1
0x180025600  jnz     short loc_180025643
0x180025602  call    cs:__imp_DisableThreadLibraryCalls
0x180025609  nop     dword ptr [rax+rax+00h]
0x18002560e  mov     rax, cs:qword_1800AC018
0x180025615  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hInst
0x18002561c  test    rax, rax
0x18002561f  jz      short loc_180025643
0x180025621  mov     ecx, 1
0x180025626  jmp     short loc_180025636
0x180025628  mov     rax, cs:qword_1800AC018
0x18002562f  test    rax, rax
0x180025632  jz      short loc_180025643
0x180025634  xor     ecx, ecx
0x180025636  mov     rdx, cs:off_1800AC008
0x18002563d  call    cs:__guard_dispatch_icall_fptr
0x180025643  mov     eax, 1
0x180025648  add     rsp, 20h
0x18002564c  pop     rbx
0x18002564d  retn
```
