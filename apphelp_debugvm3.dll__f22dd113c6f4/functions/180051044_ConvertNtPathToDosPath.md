# ConvertNtPathToDosPath

- ea: `0x180051044`
- end: `0x18005122d`
- name: `ConvertNtPathToDosPath`
- size: `489`
- prototype: `__int64 __fastcall(PCWSTR SourceString, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x180051234`

## callees

- `0x180051044`
- `0x18005915d`
- `0x180059169`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlpEnsureBufferSize` at `0x180051106`
- `ntdll!RtlpEnsureBufferSize` at `0x180051106`
- `ntdll!RtlNtPathNameToDosPathName` at `0x18005117a`
- `ntdll!RtlNtPathNameToDosPathName` at `0x18005117a`
- `ntdll!RtlFreeUnicodeString` at `0x1800511f4`
- `ntdll!RtlFreeUnicodeString` at `0x1800511f4`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800510c4`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800510c4`

## pseudocode

```c
__int64 __fastcall ConvertNtPathToDosPath(PCWSTR SourceString, void *a2, _DWORD *a3)
{
  NTSTATUS inited; // ebx
  USHORT Length; // r9
  USHORT v7; // dx
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rbx
  __int64 v11; // rcx
  PUCHAR StaticBuffer; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-E0h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-D0h] BYREF
  struct _RTL_UNICODE_STRING_BUFFER Path; // [rsp+40h] [rbp-C0h] BYREF

  *(_QWORD *)&Path.String.Length = 34078720;
  Path.ByteBuffer.ReservedForAllocatedSize = 0;
  Path.ByteBuffer.Size = 520;
  Path.ByteBuffer.Buffer = (PUCHAR)&Path.MinimumStaticBufferForTerminalNul;
  Path.ByteBuffer.StaticSize = 520;
  Path.ByteBuffer.StaticBuffer = (PUCHAR)&Path.MinimumStaticBufferForTerminalNul;
  Path.String.Buffer = &Path.MinimumStaticBufferForTerminalNul;
  Path.MinimumStaticBufferForTerminalNul = 0;
  DestinationString = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( inited >= 0 )
  {
    Length = DestinationString.Length;
    v7 = 0;
    Path.String.Length = 0;
    v8 = DestinationString.Length + 2LL;
    if ( v8 <= 0xFFFE )
    {
      if ( v8 > Path.ByteBuffer.Size )
      {
        if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v8) < 0 )
        {
          inited = -1073741801;
          goto LABEL_16;
        }
        Length = DestinationString.Length;
        v7 = Path.String.Length;
      }
      Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
      memmove_0(&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)v7 >> 1)], DestinationString.Buffer, Length);
      v9 = (unsigned __int16)(Path.String.Length + DestinationString.Length);
      Path.String.Length = v9;
      Path.String.MaximumLength = v9 + 2;
      Path.String.Buffer[v9 >> 1] = 0;
      inited = RtlNtPathNameToDosPathName(0, &Path, 0, 0);
      if ( inited >= 0 )
      {
        if ( a3 && (a2 || !*a3) )
        {
          v10 = ((unsigned __int64)Path.String.Length + 2) >> 1;
          if ( *a3 >= (unsigned int)v10 )
          {
            memcpy_0(a2, Path.String.Buffer, Path.String.Length);
            v11 = (unsigned int)(v10 - 1);
            inited = 0;
            *((_WORD *)a2 + v11) = 0;
          }
          else
          {
            *a3 = v10;
            inited = -1073741789;
          }
        }
        else
        {
          inited = -1073741811;
        }
      }
    }
    else
    {
      inited = -1073741562;
    }
  }
LABEL_16:
  StaticBuffer = Path.ByteBuffer.StaticBuffer;
  if ( Path.ByteBuffer.Buffer && Path.ByteBuffer.Buffer != Path.ByteBuffer.StaticBuffer )
  {
    *(_QWORD *)&UnicodeString.Length = 0;
    UnicodeString.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
    RtlFreeUnicodeString(&UnicodeString);
    StaticBuffer = Path.ByteBuffer.StaticBuffer;
  }
  if ( StaticBuffer )
    *(_WORD *)StaticBuffer = 0;
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180051044  mov     [rsp-8+arg_18], rbx
0x180051049  push    rbp
0x18005104a  push    rsi
0x18005104b  push    rdi
0x18005104c  lea     rbp, [rsp-1A0h]
0x180051054  sub     rsp, 2A0h
0x18005105b  mov     rax, cs:__security_cookie
0x180051062  xor     rax, rsp
0x180051065  mov     [rbp+1B0h+var_20], rax
0x18005106c  mov     rsi, rdx
0x18005106f  mov     qword ptr [rsp+2B0h+Path.String.Length], 2080000h
0x180051078  mov     edx, 208h
0x18005107d  mov     [rsp+2B0h+Path.ByteBuffer.ReservedForAllocatedSize], 0
0x180051086  lea     rax, [rbp+1B0h+Path.MinimumStaticBufferForTerminalNul]
0x18005108a  mov     [rsp+2B0h+Path.ByteBuffer.Size], rdx
0x18005108f  mov     [rsp+2B0h+Path.ByteBuffer.Buffer], rax
0x180051094  xorps   xmm0, xmm0
0x180051097  lea     rax, [rbp+1B0h+Path.MinimumStaticBufferForTerminalNul]
0x18005109b  mov     [rsp+2B0h+Path.ByteBuffer.StaticSize], rdx
0x1800510a0  mov     [rsp+2B0h+Path.ByteBuffer.StaticBuffer], rax
0x1800510a5  mov     rdx, rcx; SourceString
0x1800510a8  lea     rax, [rbp+1B0h+Path.MinimumStaticBufferForTerminalNul]
0x1800510ac  mov     rdi, r8
0x1800510af  mov     [rsp+2B0h+Path.String.Buffer], rax
0x1800510b4  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x1800510b9  xor     eax, eax
0x1800510bb  mov     [rbp+1B0h+Path.MinimumStaticBufferForTerminalNul], ax
0x1800510bf  movups  xmmword ptr [rsp+2B0h+DestinationString.Length], xmm0
0x1800510c4  call    cs:__imp_RtlInitUnicodeStringEx
0x1800510ca  mov     ebx, eax
0x1800510cc  test    eax, eax
0x1800510ce  js      loc_1800511CD
0x1800510d4  movzx   r9d, [rsp+2B0h+DestinationString.Length]
0x1800510da  xor     edx, edx
0x1800510dc  mov     [rsp+2B0h+Path.String.Length], dx
0x1800510e1  lea     r8, [r9+2]; RequiredSize
0x1800510e5  cmp     r8, 0FFFEh
0x1800510ec  jbe     short loc_1800510F8
0x1800510ee  mov     ebx, 0C0000106h
0x1800510f3  jmp     loc_1800511CD
0x1800510f8  cmp     r8, [rsp+2B0h+Path.ByteBuffer.Size]
0x1800510fd  jbe     short loc_180051125
0x1800510ff  lea     rdx, [rsp+2B0h+Path.ByteBuffer]; Buffer
0x180051104  xor     ecx, ecx; Flags
0x180051106  call    cs:__imp_RtlpEnsureBufferSize
0x18005110c  test    eax, eax
0x18005110e  jns     short loc_18005111A
0x180051110  mov     ebx, 0C0000017h
0x180051115  jmp     loc_1800511CD
0x18005111a  movzx   r9d, [rsp+2B0h+DestinationString.Length]
0x180051120  movzx   edx, [rsp+2B0h+Path.String.Length]
0x180051125  mov     rcx, [rsp+2B0h+Path.ByteBuffer.Buffer]
0x18005112a  movzx   eax, dx
0x18005112d  mov     rdx, [rsp+2B0h+DestinationString.Buffer]; Src
0x180051132  shr     rax, 1
0x180051135  mov     [rsp+2B0h+Path.String.Buffer], rcx
0x18005113a  movzx   r8d, r9w; Size
0x18005113e  lea     rcx, [rcx+rax*2]; void *
0x180051142  call    memmove_0
0x180051147  movzx   eax, [rsp+2B0h+DestinationString.Length]
0x18005114c  xor     ecx, ecx; Flags
0x18005114e  add     ax, [rsp+2B0h+Path.String.Length]
0x180051153  xor     r9d, r9d; Unknown
0x180051156  movzx   edx, ax
0x180051159  xor     r8d, r8d; PathType
0x18005115c  mov     [rsp+2B0h+Path.String.Length], dx
0x180051161  lea     eax, [rdx+2]
0x180051164  shr     rdx, 1
0x180051167  mov     [rsp+2B0h+Path.String.MaximumLength], ax
0x18005116c  mov     rax, [rsp+2B0h+Path.String.Buffer]
0x180051171  mov     [rax+rdx*2], cx
0x180051175  lea     rdx, [rsp+2B0h+Path]; Path
0x18005117a  call    cs:__imp_RtlNtPathNameToDosPathName
0x180051180  mov     ebx, eax
0x180051182  test    eax, eax
0x180051184  js      short loc_1800511CD
0x180051186  test    rdi, rdi
0x180051189  jz      short loc_1800511C8
0x18005118b  test    rsi, rsi
0x18005118e  jnz     short loc_180051194
0x180051190  cmp     [rdi], esi
0x180051192  jnz     short loc_1800511C8
0x180051194  movzx   r8d, [rsp+2B0h+Path.String.Length]; Size
0x18005119a  lea     rbx, [r8+2]
0x18005119e  shr     rbx, 1
0x1800511a1  cmp     [rdi], ebx
0x1800511a3  jnb     short loc_1800511AE
0x1800511a5  mov     [rdi], ebx
0x1800511a7  mov     ebx, 0C0000023h
0x1800511ac  jmp     short loc_1800511CD
0x1800511ae  mov     rdx, [rsp+2B0h+Path.String.Buffer]; Src
0x1800511b3  mov     rcx, rsi; void *
0x1800511b6  call    memcpy_0
0x1800511bb  lea     ecx, [rbx-1]
0x1800511be  xor     eax, eax
0x1800511c0  xor     ebx, ebx
0x1800511c2  mov     [rsi+rcx*2], ax
0x1800511c6  jmp     short loc_1800511CD
0x1800511c8  mov     ebx, 0C000000Dh
0x1800511cd  mov     rax, [rsp+2B0h+Path.ByteBuffer.Buffer]
0x1800511d2  mov     rcx, [rsp+2B0h+Path.ByteBuffer.StaticBuffer]
0x1800511d7  test    rax, rax
0x1800511da  jz      short loc_1800511FF
0x1800511dc  cmp     rax, rcx
0x1800511df  jz      short loc_1800511FF
0x1800511e1  lea     rcx, [rsp+2B0h+UnicodeString]; UnicodeString
0x1800511e6  mov     qword ptr [rsp+2B0h+UnicodeString.Length], 0
0x1800511ef  mov     [rsp+2B0h+UnicodeString.Buffer], rax
0x1800511f4  call    cs:__imp_RtlFreeUnicodeString
0x1800511fa  mov     rcx, [rsp+2B0h+Path.ByteBuffer.StaticBuffer]
0x1800511ff  test    rcx, rcx
0x180051202  jz      short loc_180051209
0x180051204  xor     eax, eax
0x180051206  mov     [rcx], ax
0x180051209  mov     eax, ebx
0x18005120b  mov     rcx, [rbp+1B0h+var_20]
0x180051212  xor     rcx, rsp; StackCookie
0x180051215  call    __security_check_cookie
0x18005121a  mov     rbx, [rsp+2B0h+arg_18]
0x180051222  add     rsp, 2A0h
0x180051229  pop     rdi
0x18005122a  pop     rsi
0x18005122b  pop     rbp
0x18005122c  retn
```
