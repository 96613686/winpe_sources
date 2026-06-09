# __commit

- ea: `0x413d88`
- end: `0x413e05`
- name: `__commit`
- size: `125`
- prototype: `int __cdecl(int FileHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x411d33`

## callees

- `0x40ec26`
- `0x40ece3`
- `0x413ce6`
- `0x413d88`

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
      && FileHandle < (unsigned int)dword_427218
      && (*(_BYTE *)(dword_427018[FileHandle >> 6] + 56 * (FileHandle & 0x3F) + 40) & 1) != 0 )
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
0x413d88  mov     edi, edi
0x413d8a  push    ebp
0x413d8b  mov     ebp, esp
0x413d8d  sub     esp, 10h
0x413d90  push    esi
0x413d91  mov     esi, [ebp+FileHandle]
0x413d94  cmp     esi, 0FFFFFFFEh
0x413d97  jnz     short loc_413DA6
0x413d99  call    __errno
0x413d9e  mov     dword ptr [eax], 9
0x413da4  jmp     short loc_413DFF
0x413da6  test    esi, esi
0x413da8  js      short loc_413DEF
0x413daa  cmp     esi, dword_427218
0x413db0  jnb     short loc_413DEF
0x413db2  mov     eax, esi
0x413db4  mov     edx, esi
0x413db6  and     eax, 3Fh
0x413db9  sar     edx, 6
0x413dbc  imul    ecx, eax, 38h ; '8'
0x413dbf  mov     eax, dword_427018[edx*4]
0x413dc6  test    byte ptr [eax+ecx+28h], 1
0x413dcb  jz      short loc_413DEF
0x413dcd  lea     eax, [ebp+FileHandle]
0x413dd0  mov     [ebp+var_8], esi
0x413dd3  mov     [ebp+var_C], eax
0x413dd6  lea     ecx, [ebp+var_1]
0x413dd9  lea     eax, [ebp+var_8]
0x413ddc  mov     [ebp+var_10], esi
0x413ddf  push    eax
0x413de0  lea     eax, [ebp+var_C]
0x413de3  push    eax
0x413de4  lea     eax, [ebp+var_10]
0x413de7  push    eax
0x413de8  call    ??$?RV_lambda_9e9de3de5fa147e2223d7db92bc10aa6_@@AAV_lambda_38ce7e780aa69e748d6df282ebc68efe_@@V_lambda_8ca6da459f0f6780f1cff60fdc3d00e5_@@@?$__crt_seh_guarded_call@H@@QAEH$$QAV_lambda_9e9de3de5fa147e2223d7db92bc10aa6_@@AAV_lambda_38ce7e780aa69e748d6df282ebc68efe_@@$$QAV_lambda_8ca6da459f0f6780f1cff60fdc3d00e5_@@@Z
0x413ded  jmp     short loc_413E02
0x413def  call    __errno
0x413df4  mov     dword ptr [eax], 9
0x413dfa  call    __invalid_parameter_noinfo
0x413dff  or      eax, 0FFFFFFFFh
0x413e02  pop     esi
0x413e03  leave
0x413e04  retn
```
