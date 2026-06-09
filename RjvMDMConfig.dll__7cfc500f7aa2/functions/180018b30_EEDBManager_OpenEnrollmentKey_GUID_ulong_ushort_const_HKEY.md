# EEDBManager::OpenEnrollmentKey(_GUID,ulong,ushort const *,HKEY__ * *)

- ea: `0x180018b30`
- end: `0x180018be9`
- name: `?OpenEnrollmentKey@EEDBManager@@CAJU_GUID@@KPEBGPEAPEAUHKEY__@@@Z`
- size: `185`
- prototype: `static int(struct _GUID *__struct_ptr, unsigned int, const unsigned __int16 *, HKEY *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018284`
- `0x18001830c`

## callees

- `0x180001c60`
- `0x180017e2c`
- `0x18001895c`
- `0x180018b30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018b6e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180018b6e`

## pseudocode

```c
int __fastcall EEDBManager::OpenEnrollmentKey(struct _GUID *a1, __int64 a2, const unsigned __int16 *a3, HKEY *a4)
{
  int result; // eax
  OLECHAR sz[40]; // [rsp+30h] [rbp-2C8h] BYREF
  wchar_t String1[40]; // [rsp+80h] [rbp-278h] BYREF
  unsigned __int16 v8[264]; // [rsp+D0h] [rbp-228h] BYREF

  v8[0] = 0;
  String1[0] = 0;
  sz[0] = 0;
  if ( StringFromGUID2(a1, sz, 39) != 39 )
    return -2147418113;
  result = EEDBTrimGuidBracket(sz, String1);
  if ( result >= 0 )
    return EEDBManager::OpenEnrollmentHKEY(HKEY_LOCAL_MACHINE, String1, 131097, a4, v8, 0x104u);
  return result;
}

```

## disassembly

```asm
0x180018b30  push    rbx
0x180018b32  sub     rsp, 2F0h
0x180018b39  mov     rax, cs:__security_cookie
0x180018b40  xor     rax, rsp
0x180018b43  mov     [rsp+2F8h+var_18], rax
0x180018b4b  xor     eax, eax
0x180018b4d  lea     rdx, [rsp+2F8h+sz]; lpsz
0x180018b52  mov     rbx, r9
0x180018b55  mov     [rsp+2F8h+var_228], ax
0x180018b5d  mov     [rsp+2F8h+String1], ax
0x180018b65  mov     [rsp+2F8h+sz], ax
0x180018b6a  lea     r8d, [rax+27h]; cchMax
0x180018b6e  call    cs:__imp_StringFromGUID2
0x180018b75  nop     dword ptr [rax+rax+00h]
0x180018b7a  cmp     eax, 27h ; '''
0x180018b7d  jz      short loc_180018B86
0x180018b7f  mov     eax, 8000FFFFh
0x180018b84  jmp     short loc_180018BCF
0x180018b86  lea     rdx, [rsp+2F8h+String1]; unsigned __int16 *
0x180018b8e  lea     rcx, [rsp+2F8h+sz]; unsigned __int16 *
0x180018b93  call    ?EEDBTrimGuidBracket@@YAJPEBGPEAG@Z; EEDBTrimGuidBracket(ushort const *,ushort *)
0x180018b98  test    eax, eax
0x180018b9a  js      short loc_180018BCF
0x180018b9c  lea     rax, [rsp+2F8h+var_228]
0x180018ba4  mov     [rsp+2F8h+var_2D0], 104h; unsigned __int64
0x180018bad  mov     r9, rbx; HKEY *
0x180018bb0  mov     [rsp+2F8h+var_2D8], rax; unsigned __int16 *
0x180018bb5  mov     r8d, 20019h; unsigned int
0x180018bbb  lea     rdx, [rsp+2F8h+String1]; String1
0x180018bc3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018bca  call    ?OpenEnrollmentHKEY@EEDBManager@@SAJPEAUHKEY__@@PEBGKPEAPEAU2@PEAG_K@Z; EEDBManager::OpenEnrollmentHKEY(HKEY__ *,ushort const *,ulong,HKEY__ * *,ushort *,unsigned __int64)
0x180018bcf  mov     rcx, [rsp+2F8h+var_18]
0x180018bd7  xor     rcx, rsp; StackCookie
0x180018bda  call    __security_check_cookie
0x180018bdf  add     rsp, 2F0h
0x180018be6  pop     rbx
0x180018be7  retn
```
