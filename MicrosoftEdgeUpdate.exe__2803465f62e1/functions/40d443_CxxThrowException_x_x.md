# _CxxThrowException(x,x)

- ea: `0x40d443`
- end: `0x40d4af`
- name: `__CxxThrowException@8`
- size: `108`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x40b98d`
- `0x40b9aa`
- `0x40c33a`
- `0x40c35a`

## callees

- `0x407eb0`
- `0x40d443`

## import_xrefs

- `KERNEL32!RaiseException` at `0x40d4a3`
- `KERNEL32!RaiseException` at `0x40d4a3`

## pseudocode

```c
void __stdcall __noreturn _CxxThrowException(void *pExceptionObject, _ThrowInfo *pThrowInfo)
{
  _ThrowInfo *v2; // edi
  ULONG_PTR v3; // ebx
  int v4; // [esp-8h] [ebp-24h]
  ULONG_PTR Arguments[3]; // [esp+10h] [ebp-Ch] BYREF

  v2 = pThrowInfo;
  v3 = 429065504;
  if ( pThrowInfo )
  {
    if ( (pThrowInfo->attributes & 0x10) == 0
      || (v4 = *(_DWORD *)pExceptionObject - 4,
          v2 = *(_ThrowInfo **)(*(_DWORD *)v4 + 24),
          (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v4 + 32))(*(_DWORD *)(*(_DWORD *)v4 + 32), v4),
          v2) )
    {
      if ( (v2->attributes & 8) != 0 )
        v3 = 26820608;
    }
  }
  Arguments[1] = (ULONG_PTR)pExceptionObject;
  Arguments[0] = v3;
  Arguments[2] = (ULONG_PTR)v2;
  RaiseException(0xE06D7363, 1u, 3u, Arguments);
}

```

## disassembly

```asm
0x40d443  push    ebp
0x40d444  mov     ebp, esp
0x40d446  sub     esp, 14h
0x40d449  mov     eax, [ebp+pExceptionObject]
0x40d44c  push    ebx
0x40d44d  push    edi
0x40d44e  mov     edi, [ebp+pThrowInfo]
0x40d451  mov     ebx, 19930520h
0x40d456  mov     [ebp+var_10], eax
0x40d459  test    edi, edi
0x40d45b  jz      short loc_40D48A
0x40d45d  test    byte ptr [edi], 10h
0x40d460  jz      short loc_40D480
0x40d462  mov     ecx, [eax]
0x40d464  sub     ecx, 4
0x40d467  push    esi
0x40d468  push    ecx
0x40d469  mov     eax, [ecx]
0x40d46b  mov     esi, [eax+20h]
0x40d46e  mov     ecx, esi
0x40d470  mov     edi, [eax+18h]
0x40d473  call    ds:___guard_check_icall_fptr
0x40d479  call    esi
0x40d47b  pop     esi
0x40d47c  test    edi, edi
0x40d47e  jz      short loc_40D48A
0x40d480  test    byte ptr [edi], 8
0x40d483  jz      short loc_40D48A
0x40d485  mov     ebx, 1994000h
0x40d48a  mov     eax, [ebp+var_10]
0x40d48d  mov     [ebp+var_8], eax
0x40d490  lea     eax, [ebp+Arguments]
0x40d493  push    eax; lpArguments
0x40d494  push    3; nNumberOfArguments
0x40d496  push    1; dwExceptionFlags
0x40d498  push    0E06D7363h; dwExceptionCode
0x40d49d  mov     [ebp+Arguments], ebx
0x40d4a0  mov     [ebp+var_4], edi
0x40d4a3  call    ds:RaiseException
0x40d4a9  pop     edi
0x40d4aa  pop     ebx
0x40d4ab  leave
0x40d4ac  retn    8
```
