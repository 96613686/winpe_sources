# Insp_SendArpChangeEvent

- ea: `0x18002f4dc`
- end: `0x18002f618`
- name: `Insp_SendArpChangeEvent`
- size: `316`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002c400`

## callees

- `0x18002f4dc`
- `0x180039a66`
- `0x180059270`

## import_xrefs

- `ntdll!NtQueryObject` at `0x18002f54a`
- `ntdll!NtQueryObject` at `0x18002f54a`
- `ntdll!EtwEventWriteNoRegistration` at `0x18002f5d9`
- `ntdll!EtwEventWriteNoRegistration` at `0x18002f5d9`
- `ntdll!RtlAllocateHeap` at `0x18002f51e`
- `ntdll!RtlAllocateHeap` at `0x18002f51e`

## string_xrefs

- `0x18002f56e`: `\REGISTRY\MACHINE\`
- `0x18002f590`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\`
- `0x18002f603`: `SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall\`

## pseudocode

```c
int __fastcall Insp_SendArpChangeEvent(HANDLE Handle)
{
  unsigned __int16 *Heap; // rax
  unsigned __int16 *v3; // rbx
  const wchar_t *v4; // rdi
  int v6; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v7[3]; // [rsp+38h] [rbp-28h] BYREF
  int v8; // [rsp+50h] [rbp-10h]
  int v9; // [rsp+54h] [rbp-Ch]

  v6 = 0;
  Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x218u);
  v3 = Heap;
  if ( Heap )
  {
    LODWORD(Heap) = NtQueryObject(Handle, ObjectNameInformation, Heap, 0x218u, 0);
    if ( (int)Heap >= 0 )
    {
      LODWORD(Heap) = *v3;
      v4 = (const wchar_t *)*((_QWORD *)v3 + 1);
      v6 = (int)Heap;
      if ( *v3 > 0x24u )
      {
        LODWORD(Heap) = wcsnicmp_0(v4, L"\\REGISTRY\\MACHINE\\", 0x12u);
        if ( !(_DWORD)Heap )
        {
          v6 -= 36;
          if ( !wcsnicmp_0(v4 + 18, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\", 0x34u)
            || (LODWORD(Heap) = wcsnicmp_0(
                                  v4 + 18,
                                  L"SOFTWARE\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\",
                                  0x40u),
                !(_DWORD)Heap) )
          {
            v7[1] = 4;
            v7[0] = &v6;
            v8 = v6;
            v7[2] = v4 + 18;
            v9 = 0;
            LODWORD(Heap) = EtwEventWriteNoRegistration(AE_LOG, AE_NEW_ARP_KEY, 2, v7);
          }
        }
      }
    }
  }
  return (int)Heap;
}

```

## disassembly

```asm
0x18002f4dc  mov     [rsp-8+arg_8], rbx
0x18002f4e1  mov     [rsp-8+arg_10], rdi
0x18002f4e6  push    rbp
0x18002f4e7  mov     rbp, rsp
0x18002f4ea  sub     rsp, 60h
0x18002f4ee  mov     rax, cs:__security_cookie
0x18002f4f5  xor     rax, rsp
0x18002f4f8  mov     [rbp+var_8], rax
0x18002f4fc  mov     rdi, rcx
0x18002f4ff  mov     [rbp+var_30], 0
0x18002f506  mov     rcx, gs:60h
0x18002f50f  mov     edx, 8; Flags
0x18002f514  mov     r8d, 218h; Size
0x18002f51a  mov     rcx, [rcx+30h]; HeapHandle
0x18002f51e  call    cs:__imp_RtlAllocateHeap
0x18002f524  mov     rbx, rax
0x18002f527  test    rax, rax
0x18002f52a  jz      loc_18002F5DF
0x18002f530  mov     r9d, 218h; ObjectInformationLength
0x18002f536  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x18002f53f  mov     r8, rax; ObjectInformation
0x18002f542  mov     edx, 1; ObjectInformationClass
0x18002f547  mov     rcx, rdi; Handle
0x18002f54a  call    cs:__imp_NtQueryObject
0x18002f550  test    eax, eax
0x18002f552  js      loc_18002F5DF
0x18002f558  movzx   eax, word ptr [rbx]
0x18002f55b  mov     rdi, [rbx+8]
0x18002f55f  mov     [rbp+var_30], eax
0x18002f562  cmp     word ptr [rbx], 24h ; '$'
0x18002f566  jbe     short loc_18002F5DF
0x18002f568  mov     r8d, 12h; MaxCount
0x18002f56e  lea     rdx, aRegistryMachin_7; "\\REGISTRY\\MACHINE\\"
0x18002f575  mov     rcx, rdi; String1
0x18002f578  call    _wcsnicmp_0
0x18002f57d  test    eax, eax
0x18002f57f  jnz     short loc_18002F5DF
0x18002f581  add     [rbp+var_30], 0FFFFFFDCh
0x18002f585  lea     rbx, [rdi+24h]
0x18002f589  mov     rcx, rbx; String1
0x18002f58c  lea     r8d, [rax+34h]; MaxCount
0x18002f590  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002f597  call    _wcsnicmp_0
0x18002f59c  test    eax, eax
0x18002f59e  jnz     short loc_18002F5FD
0x18002f5a0  lea     rax, [rbp+var_30]
0x18002f5a4  mov     [rbp+var_20], 4
0x18002f5ac  mov     [rbp+var_28], rax
0x18002f5b0  lea     r9, [rbp+var_28]
0x18002f5b4  mov     eax, [rbp+var_30]
0x18002f5b7  lea     rdx, AE_NEW_ARP_KEY
0x18002f5be  mov     r8d, 2
0x18002f5c4  mov     [rbp+var_10], eax
0x18002f5c7  lea     rcx, AE_LOG
0x18002f5ce  mov     [rbp+var_18], rbx
0x18002f5d2  mov     [rbp+var_C], 0
0x18002f5d9  call    cs:__imp_EtwEventWriteNoRegistration
0x18002f5df  mov     rcx, [rbp+var_8]
0x18002f5e3  xor     rcx, rsp; StackCookie
0x18002f5e6  call    __security_check_cookie
0x18002f5eb  lea     r11, [rsp+60h+var_s0]
0x18002f5f0  mov     rbx, [r11+18h]
0x18002f5f4  mov     rdi, [r11+20h]
0x18002f5f8  mov     rsp, r11
0x18002f5fb  pop     rbp
0x18002f5fc  retn
0x18002f5fd  mov     r8d, 40h ; '@'; MaxCount
0x18002f603  lea     rdx, aSoftwareWow643; "SOFTWARE\\Wow6432Node\\Microsoft\\Windo"...
0x18002f60a  mov     rcx, rbx; String1
0x18002f60d  call    _wcsnicmp_0
0x18002f612  test    eax, eax
0x18002f614  jnz     short loc_18002F5DF
0x18002f616  jmp     short loc_18002F5A0
```
