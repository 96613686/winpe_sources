# Kerb3961::Aes3962::StringToKey(Kerb3961::ReadOnlyString const &,Kerb3961::ReadOnlyString const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180006750`
- end: `0x1800067e6`
- name: `?StringToKey@Aes3962@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyString@2@0AEBUReadOnlyBinary@2@@Z`
- size: `150`
- prototype: `__int64 __usercall@<rax>(char *@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006750`
- `0x180011760`
- `0x1800118cc`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes3962::StringToKey(char *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  char *v7; // rcx
  unsigned __int32 v8; // ecx

  if ( *(_QWORD *)a5 == 4 )
  {
    v8 = _byteswap_ulong(**(_DWORD **)(a5 + 8));
    if ( v8 <= *((_DWORD *)a1 + 39) )
    {
      if ( v8 >= *((_DWORD *)a1 + 40) )
      {
        Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"passwordUTF8", (const char *)0xC0000001LL);
        *(_QWORD *)a2 = 0;
        *(_QWORD *)(a2 + 8) = 0;
        *(_DWORD *)(a2 + 16) = -1073741823;
        return a2;
      }
      v7 = "iterations >= m_minIterationCount";
    }
    else
    {
      v7 = "iterations <= m_maxIterationCount";
    }
  }
  else
  {
    v7 = "stringToKeyParameters.length == sizeof(uint32_t)";
  }
  Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)v7, a1);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = -1073741811;
  return a2;
}

```

## disassembly

```asm
0x180006750  push    rbx
0x180006752  sub     rsp, 20h
0x180006756  mov     rax, [rsp+28h+arg_20]
0x18000675b  mov     rbx, rdx
0x18000675e  mov     rdx, rcx; char *
0x180006761  cmp     qword ptr [rax], 4
0x180006765  jz      short loc_18000678B
0x180006767  lea     rcx, aStringtokeypar; "stringToKeyParameters.length == sizeof("...
0x18000676e  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180006773  mov     qword ptr [rbx], 0
0x18000677a  mov     qword ptr [rbx+8], 0
0x180006782  mov     dword ptr [rbx+10h], 0C000000Dh
0x180006789  jmp     short loc_1800067DC
0x18000678b  mov     rax, [rax+8]
0x18000678f  mov     ecx, [rax]
0x180006791  bswap   ecx
0x180006793  cmp     ecx, [rdx+9Ch]
0x180006799  jbe     short loc_1800067A4
0x18000679b  lea     rcx, aIterationsMMax; "iterations <= m_maxIterationCount"
0x1800067a2  jmp     short loc_18000676E
0x1800067a4  cmp     ecx, [rdx+0A0h]
0x1800067aa  jnb     short loc_1800067B5
0x1800067ac  lea     rcx, aIterationsMMin; "iterations >= m_minIterationCount"
0x1800067b3  jmp     short loc_18000676E
0x1800067b5  mov     edx, 0C0000001h; char *
0x1800067ba  lea     rcx, aPasswordutf8; "passwordUTF8"
0x1800067c1  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800067c6  mov     qword ptr [rbx], 0
0x1800067cd  mov     qword ptr [rbx+8], 0
0x1800067d5  mov     dword ptr [rbx+10h], 0C0000001h
0x1800067dc  mov     rax, rbx
0x1800067df  add     rsp, 20h
0x1800067e3  pop     rbx
0x1800067e4  retn
```
