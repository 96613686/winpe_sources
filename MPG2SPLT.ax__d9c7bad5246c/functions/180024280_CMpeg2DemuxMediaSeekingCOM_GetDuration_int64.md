# CMpeg2DemuxMediaSeekingCOM::GetDuration(__int64 *)

- ea: `0x180024280`
- end: `0x180024330`
- name: `?GetDuration@CMpeg2DemuxMediaSeekingCOM@@UEAAJPEA_J@Z`
- size: `176`
- prototype: `__int64 __fastcall(CMpeg2DemuxMediaSeekingCOM *__hidden this, __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180024280`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180024316`
- `KERNEL32!LeaveCriticalSection` at `0x180024316`
- `KERNEL32!EnterCriticalSection` at `0x1800242c0`
- `KERNEL32!EnterCriticalSection` at `0x1800242c0`

## pseudocode

```c
__int64 __fastcall CMpeg2DemuxMediaSeekingCOM::GetDuration(CMpeg2DemuxMediaSeekingCOM *this, __int64 *a2)
{
  __int64 v5; // rax
  _QWORD *v6; // rcx
  __int64 v7; // rax
  unsigned int v8; // ebx

  if ( !a2 )
    return 2147500035LL;
  v5 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 40LL) + 336LL);
  if ( v5 && *(_DWORD *)(v5 + 176) )
  {
    EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 5));
    v6 = (_QWORD *)*((_QWORD *)this + 6);
    if ( *v6 == *(_QWORD *)&TIME_FORMAT_MEDIA_TIME.Data1 && v6[1] == *(_QWORD *)TIME_FORMAT_MEDIA_TIME.Data4 )
    {
      v7 = v6[3];
    }
    else
    {
      if ( *v6 != *(_QWORD *)&TIME_FORMAT_BYTE.Data1 || v6[1] != *(_QWORD *)TIME_FORMAT_BYTE.Data4 )
      {
        v8 = -2147467259;
        goto LABEL_13;
      }
      v7 = v6[2];
    }
    *a2 = v7;
    v8 = 0;
LABEL_13:
    LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 5));
    return v8;
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x180024280  mov     [rsp+arg_0], rbx
0x180024285  push    rdi
0x180024286  sub     rsp, 20h
0x18002428a  mov     rbx, rdx
0x18002428d  mov     rdi, rcx
0x180024290  test    rdx, rdx
0x180024293  jnz     short loc_18002429F
0x180024295  mov     eax, 80004003h
0x18002429a  jmp     loc_180024325
0x18002429f  mov     rax, [rcx+30h]
0x1800242a3  mov     rcx, [rax+28h]
0x1800242a7  mov     rax, [rcx+150h]
0x1800242ae  test    rax, rax
0x1800242b1  jz      short loc_180024320
0x1800242b3  cmp     dword ptr [rax+0B0h], 0
0x1800242ba  jz      short loc_180024320
0x1800242bc  mov     rcx, [rdi+28h]; lpCriticalSection
0x1800242c0  call    cs:__imp_EnterCriticalSection
0x1800242c6  mov     rcx, [rdi+30h]
0x1800242ca  mov     rax, [rcx]
0x1800242cd  cmp     rax, qword ptr cs:TIME_FORMAT_MEDIA_TIME.Data1
0x1800242d4  jnz     short loc_1800242E9
0x1800242d6  mov     rax, [rcx+8]
0x1800242da  cmp     rax, qword ptr cs:TIME_FORMAT_MEDIA_TIME.Data4
0x1800242e1  jnz     short loc_1800242E9
0x1800242e3  mov     rax, [rcx+18h]
0x1800242e7  jmp     short loc_180024306
0x1800242e9  mov     rax, [rcx]
0x1800242ec  cmp     rax, qword ptr cs:TIME_FORMAT_BYTE.Data1
0x1800242f3  jnz     short loc_18002430D
0x1800242f5  mov     rax, [rcx+8]
0x1800242f9  cmp     rax, qword ptr cs:TIME_FORMAT_BYTE.Data4
0x180024300  jnz     short loc_18002430D
0x180024302  mov     rax, [rcx+10h]
0x180024306  mov     [rbx], rax
0x180024309  xor     ebx, ebx
0x18002430b  jmp     short loc_180024312
0x18002430d  mov     ebx, 80004005h
0x180024312  mov     rcx, [rdi+28h]; lpCriticalSection
0x180024316  call    cs:__imp_LeaveCriticalSection
0x18002431c  mov     eax, ebx
0x18002431e  jmp     short loc_180024325
0x180024320  mov     eax, 8000FFFFh
0x180024325  mov     rbx, [rsp+28h+arg_0]
0x18002432a  add     rsp, 20h
0x18002432e  pop     rdi
0x18002432f  retn
```
