# __commit

- ea: `0x41874d`
- end: `0x4187ca`
- name: `__commit`
- size: `125`
- prototype: `int __cdecl(int FileHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x415ab5`

## callees

- `0x410369`
- `0x410443`
- `0x4186ab`
- `0x41874d`

## pseudocode

```c
int __cdecl _commit(int FileHandle)
{
  int v2; // [esp+4h] [ebp-10h] BYREF
  int *p_FileHandle; // [esp+8h] [ebp-Ch] BYREF
  int v4; // [esp+Ch] [ebp-8h] BYREF

  if ( FileHandle == -2 )
  {
    *_errno() = 9;
  }
  else
  {
    if ( FileHandle >= 0
      && FileHandle < (unsigned int)dword_43E788
      && (*(_BYTE *)(dword_43E588[FileHandle >> 6] + 56 * (FileHandle & 0x3F) + 40) & 1) != 0 )
    {
      v4 = FileHandle;
      p_FileHandle = &FileHandle;
      v2 = FileHandle;
      return __crt_seh_guarded_call<int>::operator()<_lambda_9e9de3de5fa147e2223d7db92bc10aa6_,_lambda_38ce7e780aa69e748d6df282ebc68efe_ &,_lambda_8ca6da459f0f6780f1cff60fdc3d00e5_>(
               &v2,
               &p_FileHandle,
               &v4);
    }
    *_errno() = 9;
    _invalid_parameter_noinfo();
  }
  return -1;
}

```

## disassembly

```asm
0x41874d  mov     edi, edi
0x41874f  push    ebp
0x418750  mov     ebp, esp
0x418752  sub     esp, 10h
0x418755  push    esi
0x418756  mov     esi, [ebp+FileHandle]
0x418759  cmp     esi, 0FFFFFFFEh
0x41875c  jnz     short loc_41876B
0x41875e  call    __errno
0x418763  mov     dword ptr [eax], 9
0x418769  jmp     short loc_4187C4
0x41876b  test    esi, esi
0x41876d  js      short loc_4187B4
0x41876f  cmp     esi, dword_43E788
0x418775  jnb     short loc_4187B4
0x418777  mov     eax, esi
0x418779  mov     edx, esi
0x41877b  and     eax, 3Fh
0x41877e  sar     edx, 6
0x418781  imul    ecx, eax, 38h ; '8'
0x418784  mov     eax, dword_43E588[edx*4]
0x41878b  test    byte ptr [eax+ecx+28h], 1
0x418790  jz      short loc_4187B4
0x418792  lea     eax, [ebp+FileHandle]
0x418795  mov     [ebp+var_8], esi
0x418798  mov     [ebp+var_C], eax
0x41879b  lea     ecx, [ebp+var_1]
0x41879e  lea     eax, [ebp+var_8]
0x4187a1  mov     [ebp+var_10], esi
0x4187a4  push    eax
0x4187a5  lea     eax, [ebp+var_C]
0x4187a8  push    eax
0x4187a9  lea     eax, [ebp+var_10]
0x4187ac  push    eax
0x4187ad  call    ??$?RV_lambda_9e9de3de5fa147e2223d7db92bc10aa6_@@AAV_lambda_38ce7e780aa69e748d6df282ebc68efe_@@V_lambda_8ca6da459f0f6780f1cff60fdc3d00e5_@@@?$__crt_seh_guarded_call@H@@QAEH$$QAV_lambda_9e9de3de5fa147e2223d7db92bc10aa6_@@AAV_lambda_38ce7e780aa69e748d6df282ebc68efe_@@$$QAV_lambda_8ca6da459f0f6780f1cff60fdc3d00e5_@@@Z
0x4187b2  jmp     short loc_4187C7
0x4187b4  call    __errno
0x4187b9  mov     dword ptr [eax], 9
0x4187bf  call    __invalid_parameter_noinfo
0x4187c4  or      eax, 0FFFFFFFFh
0x4187c7  pop     esi
0x4187c8  leave
0x4187c9  retn
```
