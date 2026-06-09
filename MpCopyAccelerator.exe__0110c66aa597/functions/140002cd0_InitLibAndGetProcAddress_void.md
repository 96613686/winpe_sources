# InitLibAndGetProcAddress(void)

- ea: `0x140002cd0`
- end: `0x140002d1f`
- name: `?InitLibAndGetProcAddress@@YAXXZ`
- size: `79`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002b9c`
- `0x140002c2c`

## callees

- `0x140002c9c`
- `0x140002cd0`
- `0x140003c50`
- `0x140004670`

## string_xrefs

- `0x140002cd4`: `advapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall InitLibAndGetProcAddress(__int64 a1, __int64 a2, const wchar_t *a3)
{
  bool v3; // [rsp+20h] [rbp-8h]

  if ( (int)CommonUtil::UtilLoadSystemLibrary((CommonUtil *)&hLibModule, (HINSTANCE *)L"advapi32.dll", a3) >= 0
    && CommonUtil::UtilRawGetProcAddress(
         (CommonUtil *)&qword_14003C0B8,
         (__int64 (**)(void))hLibModule,
         (HINSTANCE)&stru_140027C78,
         0,
         v3) < 0 )
  {
    CleanupLibAndGetProcAddress();
  }
}

```

## disassembly

```asm
0x140002cd0  sub     rsp, 28h
0x140002cd4  lea     rdx, aAdvapi32Dll_0; "advapi32.dll"
0x140002cdb  lea     rcx, hLibModule; this
0x140002ce2  call    ?UtilLoadSystemLibrary@CommonUtil@@YAJPEAPEAUHINSTANCE__@@PEB_W@Z; CommonUtil::UtilLoadSystemLibrary(HINSTANCE__ * *,wchar_t const *)
0x140002ce7  shr     eax, 1Fh
0x140002cea  test    al, al
0x140002cec  jnz     short loc_140002D1A
0x140002cee  xor     r9d, r9d; char *
0x140002cf1  lea     r8, stru_140027C78; HINSTANCE
0x140002cf8  mov     rdx, cs:hLibModule; __int64 (**)(void)
0x140002cff  lea     rcx, qword_14003C0B8; this
0x140002d06  call    ?UtilRawGetProcAddress@CommonUtil@@YAJPEAP6A_JXZPEAUHINSTANCE__@@PEBD_N@Z; CommonUtil::UtilRawGetProcAddress(__int64 (**)(void),HINSTANCE__ *,char const *,bool)
0x140002d0b  shr     eax, 1Fh
0x140002d0e  test    al, al
0x140002d10  jz      short loc_140002D1A
0x140002d12  call    ?CleanupLibAndGetProcAddress@@YAXXZ; CleanupLibAndGetProcAddress(void)
0x140002d17  nop
0x140002d18  jmp     short $+2
0x140002d1a  add     rsp, 28h
0x140002d1e  retn
```
