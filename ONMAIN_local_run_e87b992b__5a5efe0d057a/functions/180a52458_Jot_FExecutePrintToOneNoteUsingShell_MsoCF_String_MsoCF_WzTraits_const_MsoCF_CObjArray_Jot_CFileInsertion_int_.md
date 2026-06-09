# Jot::FExecutePrintToOneNoteUsingShell(MsoCF::String<MsoCF::WzTraits> const &,MsoCF::CObjArray<Jot::CFileInsertion> &,int,Jot::COneNotePrintJobsManager &,Jot::CDefaultPrinterRestorer &,OneNote::ProgressUI::IProgress *,int)

- ea: `0x180a52458`
- end: `0x180a52cdc`
- name: `?FExecutePrintToOneNoteUsingShell@Jot@@YA_NAEBV?$String@UWzTraits@MsoCF@@@MsoCF@@AEAV?$CObjArray@VCFileInsertion@Jot@@@3@HAEAVCOneNotePrintJobsManager@1@AEAVCDefaultPrinterRestorer@1@PEAUIProgress@ProgressUI@OneNote@@H@Z`
- size: `2180`
- prototype: `char __fastcall(Jot **, __int64, unsigned int, __int64, Jot::CDefaultPrinterRestorer *, __int64, int)`
- caller_count: `1`
- callee_count: `38`
- tags: `loader_planting`

## callers

- `0x180a49640`

## callees

- `0x18002fa9c`
- `0x18005ccc0`
- `0x18005cd08`
- `0x1800718e0`
- `0x180094440`
- `0x180097660`
- `0x1801536d4`
- `0x180168858`
- `0x1801adc70`
- `0x1801ae61c`
- `0x18027dda8`
- `0x18027de34`
- `0x1802e2190`
- `0x1802e5170`
- `0x1802e5190`
- `0x18032d2d8`
- `0x18032e4fc`
- `0x18032ef70`
- `0x1803d1fb0`
- `0x1803f5de0`
- `0x1803f5f50`
- `0x180588dd0`
- `0x1805ad234`
- `0x180673ab8`
- `0x1808e7eec`
- `0x18090c454`
- `0x180912b88`
- `0x180a3ee0c`
- `0x180a3f540`
- `0x180a4a678`
- `0x180a4b450`
- `0x180a4c5e4`
- `0x180a52000`
- `0x180a52458`
- `0x180a534e8`
- `0x180a5364c`
- `0x180a536ac`
- `0x180a536e4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180a52b94`
- `KERNEL32!CloseHandle` at `0x180a52b94`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52615`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a526ea`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52755`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a5278a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a527d7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a527e5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52956`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52ba6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52c72`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52c80`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52c8e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52c9c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52caa`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52cc7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52cd5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52615`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a526ea`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52755`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a5278a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a527d7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a527e5`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52956`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52ba6`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52c72`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52c80`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52c8e`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52c9c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52caa`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52cc7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180a52cd5`

## string_xrefs

- `0x180a52572`: `FileExtension`
- `0x180a526fd`: `AlreadyPrinting`

## pseudocode

```c

```
