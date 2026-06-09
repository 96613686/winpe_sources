# ZtGetClientCertConfigLocked

- ea: `0x1800120f0`
- end: `0x1800121a9`
- name: `ZtGetClientCertConfigLocked`
- size: `185`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004310`
- `0x1800092d0`
- `0x18000e080`

## callees

- `0x180011f68`
- `0x1800120f0`
- `0x180015008`
- `0x1800152b0`

## pseudocode

```c
__int64 __fastcall ZtGetClientCertConfigLocked(int a1, _QWORD *a2)
{
  __int64 v3; // rdi
  int v4; // eax
  unsigned int v5; // ebx

  v3 = a1;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_dq(1035, 0x16u, (ULONGLONG)WPP_9def979debf939f6192d96d7c9b80830_Traceguids, a1, a2);
  if ( a2 && (*a2 = 0, (unsigned int)v3 <= 1) )
  {
    v4 = ZtCopyClientCertConfig(g_rgpZtClientCerts[v3], a2);
    v5 = v4;
    if ( v4 )
    {
      if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
        return v5;
      WPP_SF_d(1035, 0x17u, (ULONGLONG)WPP_9def979debf939f6192d96d7c9b80830_Traceguids, v4);
    }
  }
  else
  {
    v5 = 87;
  }
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 0x18u, (ULONGLONG)WPP_9def979debf939f6192d96d7c9b80830_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1800120f0  mov     [rsp+arg_0], rbx
0x1800120f5  push    rdi
0x1800120f6  sub     rsp, 30h
0x1800120fa  mov     rbx, rdx
0x1800120fd  movsxd  rdi, ecx
0x180012100  test    byte ptr cs:xmmword_18001F260+1, 8
0x180012107  jz      short loc_180012127
0x180012109  mov     edx, 16h
0x18001210e  mov     [rsp+38h+var_18], rbx
0x180012113  mov     ecx, 40Bh
0x180012118  lea     r8, WPP_9def979debf939f6192d96d7c9b80830_Traceguids
0x18001211f  mov     r9d, edi
0x180012122  call    WPP_SF_dq
0x180012127  test    rbx, rbx
0x18001212a  jz      short loc_180012175
0x18001212c  mov     qword ptr [rbx], 0
0x180012133  cmp     edi, 1
0x180012136  ja      short loc_180012175
0x180012138  lea     rax, g_rgpZtClientCerts
0x18001213f  mov     rdx, rbx
0x180012142  mov     rcx, [rax+rdi*8]
0x180012146  call    ZtCopyClientCertConfig
0x18001214b  mov     ebx, eax
0x18001214d  test    eax, eax
0x18001214f  jz      short loc_18001217A
0x180012151  test    byte ptr cs:xmmword_18001F260+1, 8
0x180012158  jz      short loc_18001219C
0x18001215a  mov     edx, 17h
0x18001215f  lea     r8, WPP_9def979debf939f6192d96d7c9b80830_Traceguids
0x180012166  mov     ecx, 40Bh
0x18001216b  mov     r9d, eax
0x18001216e  call    WPP_SF_d
0x180012173  jmp     short loc_18001217A
0x180012175  mov     ebx, 57h ; 'W'
0x18001217a  test    byte ptr cs:xmmword_18001F260+1, 8
0x180012181  jz      short loc_18001219C
0x180012183  mov     edx, 18h
0x180012188  lea     r8, WPP_9def979debf939f6192d96d7c9b80830_Traceguids
0x18001218f  mov     ecx, 40Bh
0x180012194  mov     r9d, ebx
0x180012197  call    WPP_SF_d
0x18001219c  mov     eax, ebx
0x18001219e  mov     rbx, [rsp+38h+arg_0]
0x1800121a3  add     rsp, 30h
0x1800121a7  pop     rdi
0x1800121a8  retn
```
